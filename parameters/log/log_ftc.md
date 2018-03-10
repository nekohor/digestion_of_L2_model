# 精轧温度日志

本章节主要针对FTC Log日志的参数含义及功能进行说明。

## Summary Data

Summary Data数据主要为一些控制模式的状态及计算信息，主要内容包括模拟模式（sim_mode）、模拟状态（Model mode）、设定计算次数（Count of each setup request）与状态（Setup calculation status）、控制计算状态（Control calculation status）等。

## PDI Data

PDI Data数据主要为一些PDI信息，内容包括钢种（Gradename）、成品厚度及宽度（FMcold thickness / width）、终轧温度目标值（FMX temp）、热态厚度及宽度（FM hot thickness / width）等。

## System Input Data from Operator

System Input Data from Operator主要为操作人员的输入信息，包括温度补偿值（tmp_ofs）、厚度补偿（thick_ofs）、穿带速度（thd_spd）、抛钢速度补偿（op_tail_spd）、最大出口速度（op_speed）、减速度补偿（decmll）、一般加速度（op_accel1）及高加速度（op_accel2）等。

## Setup Status Flags

Setup Status Flags主要为设定计算时一些判断条件，内容有FTC模式（ftc1_granted、ftc2_granted）、FTS模式（fts_granted）、操作工允许搞加速（burst）、FSU数据合法（head_ok）、FTC设定合法（ftc_ok）、FSU预报穿带速度限制（thd_spd_limit）、卷取入口速度限制（clr_spd_lim）、速度控制允许（permit_ctrl）、尾部降速允许（permit_decel_su）、最大轧制速度达到（flat_top）、抛钢速度达到（tail_spd_ach）、升速模式—立即（acc_immed）、升速模式—延迟（acc_delay）、升速模式—手动（acc_manual）、卷取后加速（dly_til_clr）、HTT自由冷却温度计算（free_air）、保温罩下降（covers_down）、热卷箱投用（cbx_in_use）、保温罩斜率合法（slopes_valid）、热卷箱超时（cbx_delay）、喷淋可用（sprays_avail）等。

## Control Status Flags

Control Status Flags主要为在线控制时的一些判断条件，内容有温度评价允许（classify_pce）、轧制时FTC取消（deslected）、预卷取速度限制（clr_limit）、FTC保持速度（speed_limit）、加速度限制（accel_limit）、尾部减速初始化（slwDwnInit）、新参考值要求（new_ref_req）、执行切割（div_cut）、某种速度干扰（ctrl_interfere）、切割完成（planned_dcut_done）、主传动电流限制（current_limit）、采样点温度不良（bad_temperature）、轧机传动的最高速度限制（speed_limit）、头部温度错误ok（classify_pce）、闭环状态（lpr_saturation）、干涉行动停止（reset_req）、操作干涉（opr_int）、在线喷淋改变操作（op_spray_chg）、CTC保持速度（ctc_hold）、丢失采样点（missing_smp）、板坯清除（reject）、允许尾部减速（permit_decel）等。

## Mill Distance Data

Mill Distance Data主要为温度计算时用到的一些设备距离，内容有入口到除鳞喷淋距离（entry_ds_dist）、等价入口到除鳞距离（eq_en_ds_dist）、入口到FET温度计距离（entry_pyro_dist）、等价入口到FET温度计距离（en_std_dist）、根据FDT的等价带钢长度（lenEquiv）等。

## Temperature Data

Temperature Data主要为温度计算时用到的一些计算参数、测量参数及修正系数等，内容有初始化ok（init_ok）、材料代码（matl_code）、FSU预报出口表面温度（prd_tmp_surf）、喷淋效率修正FAPP（spy_eff_mod）、FTC需要的出口目标温度（fmx_tgt_tmp）、潜热乘数（lheat_mult）、目标温度坡度率（tmp_ramp_rate）、保温辊道板坯第1段斜率（slope_hd）、总体的目标温度坡度（tmp_ramp）、保温辊道板坯第2段斜率（slope_tl）、目标温度坡度延迟距离（ramp_dly_dist）、保温辊道全长斜率（slope_full）、HTT温度数据合法（htt_data_ok）、温度斜率合法（slopes_valid）、HTT预报入口温度（temp_surf）、区域温度修正（ztmp_corr）、测量的头部穿带温度（thd_temp）、在线平均温度（avg_temp）、锁定目标温度（fmx_tgt_tmp）、平均在线目标温度（avg_targ）等。

## Spray Data

Temperature Data主要为温度计算时用到的工艺水的一些模式、设定参数、测量参数及修正系数等，涉及的工艺水有入口除鳞（fds1top）、出口除鳞（fds2top）、辊缝喷淋（fxfxrgs）、机架间冷却水（fxfxint）、逆吹水（fxfxstriptop）、消烟除尘水（fxfxfss）、机架间除鳞水（fxfxextbot）、下表冷却水（fxentbot）等，主要内容有温降（dtmp）、投用（in_srv）、自动（in_auto）、模式（in_pat）、流量（flw）、修正（mod）、效果（eff）、最小流量（flw_min）、最大流量（flw_max）等。

## Speeds

Speeds主要为温度计算时用到的设定速度与计算、测量速度，内容有FSU预报穿带速度（thd_spd）、FSU最大允许速度（max_spd）、头部最大卷取入口速度（max_clr_hd_spd）、FTC预报最大速度（veloci）、抛钢速度（tail_spd）、抛钢减速度（decmll）、停止减速机架（decel_stop_std）、测量穿带速度（thd_speed）、测量最大速度（max_speed）等。

## Lengths

Lengths主要为温度计算时用到的一些中间坯参数，主要内容有初次预报出口长度（pred_lgth_su）、中间坯长度（xfer_length）、保温辊道延迟距离（htt_delay_dist）、切割比例（divide_cut_pct）、加速延迟距离（acc_dly_dist）、尾部开始减速的出口长度（decel_dist）、重计算出口长度（pred_lgth_ctrl）、在线板坯积累长度（cum_dist）、在线控制长度（ctrl_dist）等。

## High Acceleration Information

High Acceleration Information主要为加速度计算时用到的一些判定条件与设定参数，主要内容有高加速允许（hiaccel_permit）、手动允许高加速（burst）、实例允许高加速（zoom_permit）、实例允许高加速（burst_permit）、高加速允许（zoom_permit）、高加速允许（burst_permit）、设定高加速开始温度（hac_start_tmp）、设定高加速距离（su_hac_dist）、高加速开始延迟（hi_temp）、在线高加速距离（ctrl_hac_dist）等。

## TVD Information

TVD Information主要为TVD计算时用到的一些判定条件与计算结果，主要内容有TVD计算状态（init_ok、head_ok、hiaccel_ok、body_ok、tvd_ok、tail_ok）、短坯（short_bar）、预报达到抛钢速度（tail_spd_ach）、采样长度（smp_length）、一般加速度（accel_norm）、实例延迟距离（delay_dist）、一般加速度调整（accel）、温度参考锁定延迟（lockon_delay）、实例辊道加速度（accel_rot）、加速度延迟距离（acc_dly_dist）、FM入口机架停留时间（fme_res_time）、FTC预报最大速度（pred_max_spd）、减速开始机架（decStand）、F1抛钢前减速开始距离（decDist）等。

## FTHMI Operator Display Data

主要为TVD计算时用到的一些判定条件与计算结果，主要内容有加速度延迟距离（acc_dly_dist）、预卷取加速前距离（pre_clr_stp_dist）、卷取入口速度（clr_ent_spd）等。

## FTPRP Model Table Data

FTPRP Model Table Data主要为FTPRP表中定义的一些参数，用于温度与TVD计算，主要内容有钢种族（family）、厚度索引代码（grt_idx）、实例延迟距离（delay_dist）、卷取后加速（dly_til_clr）、抛钢速度（tail_spd）、减速度（decmll）、头部最大卷取入口速度（max_clr_hd_spd）、停止减速机架（decel_stop_std）、实例允许高加速（burst_permit）、高加速度（accel_hi）、实例允许高加速（zoom_permit）、实例辊道加速度（accel_rot）、最小一般加速度（accel_norm_min）、总体目标温度坡度（tmp_ramp）、最大一般加速度（accel_norm_max）、目标温度坡度延迟距离（ramp_dly_dist）、移除机架（dec_std_adj）、轧制速度调整（spd_dec_adj）等。

## Setup FTAPP Model Table Data

Setup FTAPP Model Table Data主要为FTAPP表中定义的一些参数，用于温度计算自学习项，主要内容有允许加速（perm_update）、更新次数（updates）、钢种族（family）、厚度索引代码（grt_idx）、加速度索引（accel_idx）、温度补偿（temp_vernier）、一般加速度（accel_norm）、温度修正第1段（temp_corr[0]）、基础加速度（accel_base）、温度修正第2段（temp_corr[1]）、平均全长斜率（avg_slope）等。

## Feedback FTAPP Model Table Data

Feedback FTAPP Model Table Data主要为温度自学习项的计算结果，主要内容有自学习计算ok（adapt_calcs_ok）、更新次数（updates）、加速度计算完成（acc_calcs_done）、温度计算完成（temp_calcs_done）、平均在线一般加速度（avg_accel）、平均在线目标温度（avg_targ）、平均在线温度（avg_temp）、头部斜率平均加速度调整（accAdjH）、全长斜率加速度调整（accAdjF）、在线一般加速度调整（adj_accel）、加速度差（accDiff）、一般加速度（accel_norm）、温度补偿（temp_vernier）、基础加速度（accel_base）、温度修正第1段（temp_corr[0]）、平均全长斜率（avg_slope）、温度修正第2段（temp_corr[1]）、测量截距第1段（meas_intercept[0]）、测量截距第2段（meas_intercept[1]）、测量斜率第1段（meas_slope[0]）、测量斜率第2段（meas_slope[1]）、测量采样点第1段（meas_smps[0]）、测量采样点第2段（meas_smps[1]）、重计算截距第1段（pred_intercept[0]）、重计算截距第2段（pred_intercept[1]）、重计算截距第1段（pred_slope[0]）、重计算截距第2段（pred_slope[1]）、重计算采样点第1段（pred_smps[0]）、重计算采样点第2段（pred_smps[1]）等。

## Performance Data

Performance Data主要为温度带分类数据，主要内容有FTC需要的出口目标温度（fmx_tgt_tmp）、锁定目标温度（fmx_tgt_tmp）、温度评价允许（classify_pce）、规格中的比例长度（percent_on）、规格范围（perf_val）等。

## Basic Sample Data

Basic Sample Data主要输出了样本的数据，主要为速度、加速度、判断条件等，内容有采样点序号、轧机状态、带钢长度、逝去时间、出口速度、加速度参考值、加速、减速、测量温度、加权温度、温度参考值、最大速度、操作干涉、电流限制、CTC保持、最高速度、操作改变、新参考值、温度异常、高加速度等。

## FME, Predicted and Spray SampleData

FME, Predicted and Spray SampleData主要输出了样本的数据，主要为水量与温度信息，内容有采样点序号、轧机状态、带钢长度、预报FET、加权FET、表面FET、测量FDT、预报表面FDT、前馈预报表面温度、前馈温度错误、目标温度加权、前馈温度修正、前馈调整、立即调整、温度补偿、测量温度不良、测量流量、反馈标志、设定流量、喷淋控制、高加速控制等。

 