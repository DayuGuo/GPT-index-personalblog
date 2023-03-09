# 引
配置好 Wordpress 后，「用户提交和回复评论」并不能收到邮件提醒，还需要设置 SMTP， Wordpress 才能正常发送电子邮件。
笔者之前试过 QQ 邮箱的 SMTP 功能，其配置麻烦。且使用几次后，就禁封了我的帐号（尝试了两次均如此），至今不知原因，故尝试使用 Outlook。
# 配置 Wordpress 的专用邮箱
Outlook 可设置多个别名，在 `设置 > 邮件 > 同步电子邮件 > 管理或选择主别名` 中，添加新别名。设置与个人网站相关的邮件名，能增加邮件的信度，便于收件方理解。
另外，在 `设置 > 邮件 > 同步电子邮件 > POP 和 IMAP` 中，将 POP 选项，勾选为 `是`。
![[Pasted image 20230201101519.png]]

【可选】接下来，我们可以配置一个邮箱规则，将所有 Wordpress 提醒（博客）相关的邮件，自动化（如下图）。
![[Pasted image 20230201101916.png]]

# Easy WP SMTP 设置
先在 Wordpress 插件市场中下载 Easy WP SMTP。这个软件是我使用过多个软件后，觉得最清爽的。
- From Email Address：完整的 Outlook 电子邮件地址 
- From Name：你期望收件方看到的名称
- SMTP Host：smtp.office365.com
- Type of Encryption：STARTTLS
- SMTP Port：587
- SMTP Authentication：Yes
- SMTP Username：完整的 Outlook 电子邮件地址 
- SMTP Password：Outlook 登陆密码
随后，可以在「Test Email」中发送测试邮件。显示「Test email was successfully sent. No errors occurred during the process.」，即说明设置成功。
设置到这里，我卡住了很久，测试邮件都发送失败了，查了很久资料才在 Outlook 官方社区发现原因，这似乎是一个比较新的 Bug，并非所有人都会碰到。
- 转到 https://account.live.com/activity , 使用受影响帐户的电子邮件地址和密码登录；
- 在「近期活动」中，查找与链接错误时间匹配的「会话类型」（IP 地址为 Wordpress 托管服务器的地址）；
- 选择「这是我」授权链接。
- 重新发送测试邮件。
# 设置 Comment Reply Email Notification
在 Wordpress 插件商店中下载 Comment Reply Email Notification，无需设置，即可。

# 美化
这部分，我参考的这篇文章：[WordPress 评论审核、评论回复通知美化](https://www.moeelf.com/archives/274.html)，我就稍微改了一下颜色。
![[Pasted image 20230201113241.png]]
代码如下，复制代码添加到 `wp-content/themes/[the name of your theme]` 中的 `functions.php` 文件末尾即可：
```
//WordPress 评论回复邮件通知代码
function comment_mail_notify($comment_id) {
    $admin_email = get_bloginfo ('admin_email');
    $blogname = wp_specialchars_decode(get_option('blogname'), ENT_QUOTES);
    $comment = get_comment($comment_id);
    $parent_id = $comment->comment_parent ? $comment->comment_parent : '';
    $spam_confirmed = $comment->comment_approved;
    global $wpdb;
    $comments_waiting = $wpdb->get_var("SELECT count(comment_ID) FROM $wpdb->comments WHERE comment_approved = '0'");
    if (($parent_id != '') && ($spam_confirmed != 'spam') && ($to != $admin_email)) {
        $wp_email = 'no-reply@' . preg_replace('#^www\.#', '', strtolower($_SERVER['SERVER_NAME']));
        $to = trim(get_comment($parent_id)->comment_author_email);
        $subject = '您在 [' . $blogname . ']' . ' 中的留言有了新回复！';
        $message = '<div style="background-color:white;border-left: 2px solid #555555;box-shadow:0 1px 3px #AAAAAA;line-height:180%;padding:0 15px 12px;width:500px;margin:50px auto;color:#555555;font-family:"Source Sans Pro","Hiragino Sans GB","Microsoft Yahei",SimSun,Helvetica,Arial,Sans-serif,monospace;font-size:14px;"> 
            <h2 style="border-bottom:1px solid #DDD;font-size:14px;font-weight:normal;padding:13px 0 10px 8px;"><span style="color: #d7221e;font-weight: bold;">&gt; </span>您在 <a style="text-decoration:none; color:#d7221e;font-weight:600;" href="' . home_url() . '">' . $blogname . '</a> 的留言有回复啦！</h2><div style="font-size: 14px; color: #777; padding: 0 10px; margin-top: 18px;">
            <p><b>' . trim(get_comment($parent_id)->comment_author)  . '</b> 同学，您曾在文章<b>《' . get_the_title($comment->comment_post_ID) . '》</b>上发表评论:</p>
            <p style="background: #F5F5F5; padding: 10px 15px; margin: 18px 0;">' . nl2br(strip_tags(get_comment($parent_id)->comment_content)) . '</p>
            <p>' . '<b>' . trim($comment->comment_author) . '</b>'. ' 给您的回复如下:</p>
            <p style="background: #F5F5F5; padding: 10px 15px; margin: 18px 0;">' . nl2br(strip_tags($comment->comment_content)) . '</p>
            <p>您可以点击 <a style="text-decoration:none; color:#d7221e" href="' . htmlspecialchars(get_comment_link($parent_id)) . '">查看完整的回复內容</a>，也欢迎再次光临 <a style="text-decoration:none; color:#d7221e"
            href="' . home_url() . '">' . $blogname . '</a>。祝您生活愉快！</p>
            <p style="padding-bottom: 15px;">(此邮件由系统自动发出,请勿直接回复!)</p></div></div></td></tr></tbody></table></div>';
        $from = "From: \"" . get_option('blogname') . "\" <$wp_email>";
        $headers = "$from\nContent-Type: text/html; charset=" . get_option('blog_charset') . "\n";
        wp_mail( $to, $subject, $message, $headers );
    }
 
    //文章有新评论时通知管理员
    if ($parent_id == '' && (trim($comment->comment_author_email) != trim($admin_email)) && ($spam_confirmed != 'spam') && ($comment->comment_approved != 0)){
        $wp_email = '';
        $subject = '在「' . $blogname .'」的文章《'. get_the_title($comment->comment_post_ID) .'》一文有新的评论';
        $message = '<div style="background-color:white;border-left: 2px solid #555555;box-shadow:0 1px 3px #AAAAAA;line-height:180%;padding:0 15px 12px;width:500px;margin:50px auto;color:#555555;font-family:"Source Sans Pro","Hiragino Sans GB","Microsoft Yahei",SimSun,Helvetica,Arial,Sans-serif,monospace;font-size:14px;"> 
            <h2 style="border-bottom:1px solid #DDD;font-size:14px;font-weight:normal;padding:13px 0 10px 8px;"><span style="color: #d7221e;font-weight: bold;">&gt; </span><a style="text-decoration:none;color: #d7221e;" href="' . home_url() . '">' . $blogname . '</a> 博客有新的评论啦！ </h2> 
            <div style="padding:0 12px 0 12px;margin-top:18px;"> 
            <p><b>'. $comment->comment_author . '</b> 同学在文章<b>《' . get_the_title($comment->comment_post_ID) . '》</b>上发表评论:</p> 
            <p style="background-color: #f5f5f5;border: 0px solid #DDD;padding: 10px 15px;margin:18px 0;">' . $comment->comment_content . '</p> 
            <p>您可以点击 <a style="text-decoration:none; color:#d7221e" href="' . htmlspecialchars(get_comment_link($parent_id)) . '">查看完整的回复內容</a>，也欢迎再次光临 <a style="text-decoration:none; color:#d7221e" href="' . home_url() . '">' . $blogname . '</a>。祝您生活愉快！</p></div></div>';
        $headers = "Content-Type: text/html; charset=" . get_option('blog_charset') . "\n";
        wp_mail( $admin_email, $subject, $message, $headers );
    }
 
    //评论需要审核时通知
    if ($parent_id == '' && (trim($comment->comment_author_email) != trim($admin_email)) && ($spam_confirmed != 'spam') && ($spam_confirmed != 'trash')  && ($comment->comment_approved == 0)){
        $wp_email = '';
        $subject = '在「' . $blogname .'」的文章《' . get_the_title($comment->comment_post_ID) . '》中有新的评论需要审核';
        $message = '<div style="background-color:white;border-left: 2px solid #555555;box-shadow:0 1px 3px #AAAAAA;line-height:180%;padding:0 15px 12px;width:500px;margin:50px auto;color:#555555;font-family:"Source Sans Pro","Hiragino Sans GB","Microsoft Yahei",SimSun,Helvetica,Arial,Sans-serif,monospace;font-size:14px;"> 
            <h2 style="border-bottom:1px solid #DDD;font-size:14px;font-weight:normal;padding:13px 0 10px 8px;"><span style="color: #d7221e;font-weight: bold;">&gt; 「 </span><a style="text-decoration:none;color: #d7221e;" href="' . home_url() . '">' . $blogname . '」</a> 中有一条评论等待您的审核 </h2> 
            <div style="padding:0 12px 0 12px;margin-top:18px;"> 
            <p><b>'. $comment->comment_author . '</b> 同学在文章<b><a style="text-decoration:none;color: #d7221e;" href="' . get_permalink($comment->comment_post_ID) . '">《' . get_the_title($comment->comment_post_ID) . '》</a></b>上发表评论:</p> 
            <p style="background-color: #f5f5f5;border: 0px solid #DDD;padding: 10px 15px;margin:18px 0;">' . $comment->comment_content . '</p> 
            <p><a style="text-decoration:none;color: #5A5A5A;" href="'. admin_url( "comment.php?action=approve&c={$comment_id}#wpbody-content" ) . '">[批准评论]</a> | <a style="text-decoration:none;color: #5A5A5A;" href="'. admin_url( "comment.php?action=trash&c={$comment_id}#wpbody-content" ) . '">[移至回收站]</a>。您还可以：<a style="text-decoration:none; color:#5A5A5A" href="' . admin_url( "comment.php?action=delete&c={$comment_id}#wpbody-content" ) . '">永久删除评论</a> | <a style="text-decoration:none;color: #5A5A5A;" href="'. admin_url( "comment.php?action=spam&c={$comment_id}#wpbody-content" ) . '">标记为垃圾评论</a>
            <p>当前有 ' . $comments_waiting . ' 条评论等待审核。请移步<a style="text-decoration:none;color: #d7221e;" href="' . admin_url('edit-comments.php?comment_status=moderated#wpbody-content') . '">审核页面</a>来查看。</p>也欢迎再次光临 <a style="text-decoration:none; color:#d7221e" href="' . home_url() . '">' . $blogname . '</a>。祝您生活愉快！</p></div></div>';
        $headers = "Content-Type: text/html; charset=" . get_option('blog_charset') . "\n";
        wp_mail( $admin_email, $subject, $message, $headers );
    }
}
add_action('comment_post', 'comment_mail_notify');
```

使用的时候请关闭 `设置 > 讨论 > Email me whenever` 中的两个选项，并保存。否则系统会发送两封邮件给你，一封是美化过的，一封是原始版。

![[Pasted image 20230201131043.png]]