[[Blog_MOC]] #Permanent

# 命令行查询电池健康和电池循环次数
在 macbook 自带的终端中，输入以下代码：
```
ioreg -rn AppleSmartBattery | grep -i capacity
```
得到如下信息：
```
ioreg -rn AppleSmartBattery | grep -i capacity
      "AppleRawCurrentCapacity" = 4280
      "AppleRawMaxCapacity" = 4280
      "MaxCapacity" = 4280
      "CurrentCapacity" = 4280
      "LegacyBatteryInfo" = {"Amperage"=0,"Flags"=5,"Capacity"=4280,"Current"=4280,"Voltage"=12620,"Cycle Count"=253}
      "BatteryData" = {"PMUConfigured"=0,"FccComp2"=4280,"ResScale"=117,"SystemPower"=1108033165,"Qmax"=(4998,5012,4992),"DesignCapacity"=5088,"CellVoltage"=(4206,4207,4207),"PassedCharge"=0,"RaTableRaw"=(<00000083007d0091007f009100620073007500730078007d00a700f101c302ac>,<0000008e0070007d006e00880057005e005d00610068006f008d00ba01aa029d>,<00000096007e009200800090006000650068006d00720072008900f501b60299>),"StateOfCharge"=100,"PresentDOD"=(9,9,9),"Flags"=557318657,"DataFlashWriteCount"=3854,"DOD0"=(1568,1552,1536),"ChemID"=6262,"AdapterPower"=1108296361,"CycleCount"=253,"Voltage"=12620,"GaugeFlagRaw"=16608,"FccComp1"=4492,"BatteryState"=<000000000000000043e4001009000100>,"ManufactureDate"=61783980128306,"LifetimeData"={"TotalOperatingTime"=21768,"UpdateTime"=1665636536,"AverageTemperature"=1,"TimeAtHighSoc"=<4e010000b2210000fe0e000000000000>},"Serial"="F8Y01670HZWJ7PYC1"}
      "DesignCapacity" = 5088
```
 当前容量（CurrentCapacity） 为 4280，设计容量（DesignCapacity）为 5088，电池健康程度及为 84%。电池循环次数（Cycle Count）为 253。
 # coconutBattery
 [coconutBattery](https://www.coconut-flavour.com/coconutbattery/) 可以很方便的查看 macbook 的电池健康状况等全部信息，免费功能已经完全够用。
 ![[Pasted image 20221013130126.png]]
