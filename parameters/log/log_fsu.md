# 精轧日志

FSU coursef内容可以分为以下几个大块，分别如下：

## 基本信息

Ø  钢卷基本信息

卷号、钢种牌号、钢种族、材质代码、厚度代码、宽度代码、喷淋代码、牌号代码、加热炉号、压下分配模式等

未理解：Sim_mode、second_dcut、cold_lim、hot_lim、hot_slab、tmge_control

Ø  板坯及中间坯信息

厚度、宽度、长度、重量、表面温度、平均温度

Ø  目标数据

目标厚度、温度、宽度、速度等

Ø  化学成分信息

C      Si     Mn    Ni     Cr     V  Nb     Mo    Ti     B     Cu Sb    Mg     Fe     Zn    Se     TePbBe     Cd    Ce     Co     Ge    Ta

## 头点设定计算及实际数据

Ø  轧制力相关计算数据

各机架计算出口厚度x-thk；

各机架计算出口宽度x-wid；

各机架轧辊设定速度rollspeed；

各机架设定计算速度setspeed；

各机架前滑forwdslip；

各机架后滑back slip；

各机架带钢轧制力stripforce；

各机架参数表载荷分配fprpload；

各机架操作输入载荷oprload；

各机架ssu设定反馈载荷ssu load；

各机架初始设定载荷分配initload；

各机架目标载荷分配targetload；

各机架最终载荷分配finalload；

Ø  变形抗力相关计算数据

绝对压下量draft

相对压下量pu draft

变形区温度rb temp

平均温度avg temp

表面温度surf temp

应力状态影响系数forceQp

接触弧长arcon

压扁半径Deform

压扁半径与原始半径比值Rd/R

咬入角bite angel

变形抗力deformresist

应变速率stain rate

变形抗力计算相关数值ks、kk、n、m、ad

Ø  轧制力矩相关计算数据

轧制力矩rolltorque

单位轧制力矩比例putorque

转速rpm

主传动力矩motortorque

主传动力矩限制Mt.torquelimit

主传动功率power

轧制功率power def

摩擦功率power fri

功率调节参数Powermult

变形热温升dtempdeform

摩擦热温升dtempfrict   

传导热温度损失dtempcond

Ø  功率相关计算数据

Power shaft

Pct power

Power ten

Power torque

Op tensM

Lpr out_svc

出口张力exittension

Dfdhx

Dtmp avg

最大轧制力限制forcemax

Fst limreasons

Lst limreasons

Ø  变形抗力及轧制力相关自学习数据

Z-LK变形抗力自学习系数

Str_idx应变速率索引

Tmp_idx温度索引

Read 布尔型变量

Z-LPH*Z_LPB*Z_BP=Z_P

轧制力自学习计算

Z_LGH*Z_LGB*Z_BG=Z_G

功率自学习计算

轧制力分加热炉计算：0.5*前1+0.1*前2+0.4*同炉最近（Coil for same Fce in3 latest coils）验证

## 中点设定计算及实际数据

Set speed为“—”

## 辊缝设定计算信息

轧辊辊缝Roll gap

轧辊弹跳Sm

标定轧辊弹跳Sm0

油膜厚度Soil

标定油膜厚度Soil0

轧辊弯辊补偿Sb

轧辊窜辊位置补偿Swrs

轧辊磨损补偿Srw

轧辊热膨胀补偿Srh

厚度自学习Zbs

Sset=Sm0-Soil0+h-Sm+Soil+Sb+Swrs-Srh-Srw+Szset+Zbs

标定轧机刚度M0

轧制时的轧机刚度M

弯辊力bend force

平衡力blanc force

窜辊位置 shiftposition

轧辊磨损增益系数Srwgain

热膨胀增益系数Srhgain

轧辊磨损 Roll srw

轧辊热膨胀Roll srh

标定速度 zerospeed

标定轧制力 zeroforce

## 工作辊及支撑辊信息

直径dia

平均温度avg_t

表面温度Srf_t

膨胀量expans

磨损量wear

希区柯克常数Hitch0.0224/0.0247

杨氏模量Young’s206703/190000

材质代码 matl ID

是否为CVC辊 CVC

辊形profile   cvcl

轧制块数 count

## 轧制润滑相关数据

辊缝润滑油流量（上下）Lubri_flow

布尔型：是否要求投用(上下)on_reqest

布尔型：辊缝润滑状态 RGLconti

布尔型：辊缝润滑头尾状态roll_lube

## 与一级相关数据（AGC 、活套等）

轧件刚度plasticity coef

单位入口厚度变化引起的轧制力变化dforce denthick  

单位出口厚度变化引起的轧制力变化dforce dexthick

单位变形抗力变化引起的轧制力变化dforce ddeform

单位前张力变化引起的轧制力变化dforce dftension

单位后张力变化引起的轧制力变化dforce dbtension

敏感因子sensitivity factor

单位入口厚度变化引起的轧制力矩变化dtorque denthick

单位出口厚度变化引起的轧制力矩变化dtorque dexthick

单位变形抗力变化引起的轧制力矩变化 dtorque ddeform

单位前张力变化引起的轧制力矩变化 dtorque dftension

单位后张力变化引起的轧制力矩变化 dtorque dbtension

## 喷淋设定信息（头中尾）

喷淋水导致温度的变化量dtmp

flw 、Mod、eff

最大最小水量

## 采样点信息

头点、中点、尾点

开始位置、结束位置、采样点长度