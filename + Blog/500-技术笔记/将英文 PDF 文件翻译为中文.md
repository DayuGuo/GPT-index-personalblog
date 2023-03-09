#Permanent
[[Blog_MOC]] 

英文文章的速读在工作生活中都很必要，直接阅读英文文本的速度往往不如母语。本文提供三种方法，帮助大家将英文 PDF 文件翻译为中文。
# DeepL
- 方法：仅需要将文件上传到 DeepL 软件
- 5 MB 以下可以免费翻译；5 MB 以上需要会员，价格较贵
- 导出为 `.pdf` 格式，双栏的论文依旧保留排版结构。
- 翻译质量很高，翻译速度快
![[Screenshot 2022-10-28 at 11.46.53.png]]
# Pdf2docx + Words 内置翻译功能
- 需要掌握基础 Python 知识
- 免费
- 导出为 `.docx` 格式，保持双栏排版结构
- 翻译质量高，翻译速度快
![[Screenshot 2022-10-28 at 11.50.36.png]]
先要使用 Python 将 `.pdf` 转为 `.docx` 格式
```
pip install pdf2docx

from pdf2docx import parse

pdf_file = '#这里替换为 pdf 文件路径，如/Users/zhaoyuguo/Github-database/Radiomics-Schistosomiasis/1.docx'
docx_file = '#这里替换为导出 docx 文件路径，如/Users/zhaoyuguo/Github-database/Radiomics-Schistosomiasis/1.docx'

# convert pdf to docx
parse(pdf_file, docx_file)

```
打开 `.docx` 文件，在 `Review - Translate - Translate Document` 中翻译文档即可。
![[Pasted image 20221028115313.png]]

# 在线转格式 + Words 内置翻译

使用 [在线转格式网站](https://tinywow.com/pdf/to-word) ，将 `.pdf` 转为 `.docx` 格式。不过，保持排版的格式转换方式，转换的很慢。所以我选用了不保存排版的格式转换方式。后续翻译步骤与上一种方法一样。
- 方法简单
- 免费
- 翻译质量有保障
- 排版混乱，阅读难度比前两种大一些。
![[Screenshot 2022-10-28 at 11.58.33.png]]
