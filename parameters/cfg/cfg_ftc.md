# FTC CFG配置文件

FTC CFG配置共计33个，其中涉及到模型参数配置的有4个，故本文主要针对这4张表的参数含义及功能进行说明。

## cfg_clc

| 参数             | 含义             | 功能            |
| -------------- | -------------- | ------------- |
| acc_corr_gain  | 加速度增益          | 加速度计算时乘数因子    |
| err_corr_gain  | 温度误差校正增益       | 温度偏差计算时乘数因子   |
| imd_err_gain   | 直接前馈温度修正增益     | 立即温度偏差计算时乘数因子 |
| init_ffwd_gain | 初始前馈温度修正增益     | 前馈温度偏差计算时乘数因子 |
| init_imd_gain  | 初始直接前馈温度修正增益   | 前馈温度偏差计算时乘数因子 |
| k1_1           | 增益系数           | 温度偏差计算时乘数因子   |
| k1_2           | 增益系数           | 温度偏差计算时乘数因子   |
| lo_tmp_gain_hd | 冷卷头部加速度增益      | 冷卷温度偏差计算时乘数因子 |
| lo_tmp_gain_tl | 冷卷尾部加速度增益      | 冷卷温度偏差计算时乘数因子 |
| min_counter    | 最小控制周期         | 加速度控制闭环启动最小计数 |
| prev_ffwd_gain | 前馈积分增益         | 前馈温度偏差计算时乘数因子 |
| switch_db      | 加速度变化开关信号的温度死区 | 温度偏差的判断条件     |
| td_1           | 超前时间           | 温度偏差计算时乘数因子   |
| td_2           | 超前时间           | 温度偏差计算时乘数因子   |
| temp_error_db  | 加速度限制温度死区      | 加速度限制的判断条件    |
| thread_vel_db  | 穿带速度死区         | F7出口速度的判断条件   |
| tn_1           | 滞后时间           | 温度偏差计算时乘数因子   |
| tn_2           | 滞后时间           | 温度偏差计算时乘数因子   |

## cfg_hiaccel

| 参数              | 含义           | 功能                    |
| --------------- | ------------ | --------------------- |
| burst_start_db  | brust加速开始死区  | 加速度开始判断条件             |
| burst_stop_db   | brust加速停止死区  | 加速度结束判断条件             |
| cold_tmp_lim    | 冷极限          | 低温度偏差判断条件             |
| del_temp_lim    | 温度变化极限值      | 加速度结束判断条件             |
| fdbk_pred_gain  | 预报温升增益       | 预报温差计算的乘数因子           |
| ffwd_corr_lim   | 前馈修正限制       | 温度偏差修正限制              |
| ffwd_err_gain   | 前馈预报错误增益     | 温度偏差计算的乘数因子           |
| ffwd_permit     | 前馈控制允许       | 前馈控制判断条件              |
| hot_tmp_lim     | 热极限          | 高温度偏差判断条件             |
| min_hac_lgth    | 最小高加速长度      | Zoom加速判断条件            |
| norm_acc_permit | 保持加速度喷淋控制允许  | 喷淋控制的判断条件             |
| num_vrn_spys    | 反馈喷嘴数        | 反馈喷嘴数                 |
| pre_acc_permit  | 保持加速度前喷淋控制允许 | 卷取前加速判断条件             |
| pre_clr_permit  | 卷取前喷淋控制允许    | 卷取前加速判断条件             |
| reg_lockon_db   | 温度调节设定值      | 区域温度计算判断条件            |
| reg_permit      | 区域温度调节允许     | 区域温度计算判断条件            |
| reverse_ctrl    | 反转控制         | 反转控制判断条件              |
| spy_ctrl_dly    | 喷淋控制延迟时间     | 头部喷淋控制延迟时间            |
| tmp_err_lim     | 最大错误允许修正     | 温度误差边界条件              |
| tot_pred_gain   | 排除预报温升增益     | 剩余预报温度偏差计算时的乘数因子      |
| vrn_permit      | 反馈允许         | 最后一个喷淋可用做vernier的判断条件 |
| zoom_start_db   | zoom加速开始死区   | Zoom加速开始判断条件          |
| zoom_stop_db    | zoom加速停止死区   | Zoom加速结束判断条件          |

## cfg_model

| 参数             | 含义            | 功能            |
| -------------- | ------------- | ------------- |
| acc_dev        | 加速度偏差         | 一般加速度的限制偏差    |
| acc_lim        | 自学习限制         | 加速度偏差自学习限制    |
| accel_max      | 最大加速度         | 一加加速度最大值      |
| accel_min      | 最小加速度         | 一加加速度最小值      |
| corr_err_gain  | 温度斜率增益        | 分段斜率自学习计算增益   |
| corr_err_lim   | 温度斜率限制        | 分段斜率自学习计算判断条件 |
| corr_limit     | 温度斜率修正限制      | 分段斜率自学习计算判断条件 |
| fbk_percent    | 反馈比例          | 反馈控制长度比例      |
| fbk_permitted  | 反馈允许          | 反馈控制判断条件      |
| hd_slope_gain  | 头部斜率增益        | 头部加速度计算增益     |
| hi_acc_gain    | 加速度高增益        | 一般加速度计算时的大的增益 |
| hi_terr_lim    | 适应温度误差高的限制    | 一般加速度计算时的大的限制 |
| min_adapts     | 最小适应数         | 一般加速度计算的判断条件  |
| neg_slope_gain | 负斜率增益         | 全长斜率负斜率计算增益   |
| norm_acc_gain  | 一般加速度增益       | 一般加速度计算时的增益   |
| norm_terr_lim  | 正常适应温度误差限制    | 一般加速度计算时的限制   |
| pos_slope_gain | 正斜率增益         | 全长斜率正斜率计算增益   |
| shadowing      | 遮蔽            | 分段斜率计算的判断条件   |
| skid_limit     | 水印限制          | 反馈控制的判断条件     |
| slope_dev_lim  | 中间-头部温度斜率偏差限制 | 头部加速度计算偏差限制   |
| terr_gain      | 温度误差增益        | 温度偏差计算增益      |
| vern_err_gain  | 温度偏差补偿增益      | 温度偏差计算增益      |
| vern_err_lim   | 温度偏差补偿限制      | 温度偏差计算的进入限制   |
| vernier_limit  | 温度补偿限制        | 分段温度自学习计算判断条件 |

## cfg_temperature

| 参数               | 含义        | 功能             |
| ---------------- | --------- | -------------- |
| classify         | 温度带分类允许   | 温度带分类          |
| fbk_smp_offset   | 反馈采样点补偿   | 反馈喷淋控制的判断条件    |
| filter_time      | 锁定过滤时间    | FDT温度过滤时间      |
| fme_dtmp_lim     | FME样本温差限制 | FME样本间温差极限值    |
| fme_pyro_lim     | FME下限     | FME温度低温极值      |
| fmx_dtmp_lim     | FMX样本温差限制 | FMX样本间温差极限值    |
| head_trim        | 头倾度       | 头部开始位置         |
| hi_fme_filter    | FME过滤上增益  | FME高增益系数       |
| hi_fmx_filter    | FMX过滤上增益  | FMX高增益系数       |
| hi_lockon_filter | 上锁定增益     | 锁定加权温度计算的大系数   |
| is_override_perm | 忽略喷淋模式    | 喷淋模式忽略的判断条件    |
| limit            | 温度带锁定限制   | 温度带区分类极限值      |
| lo_fme_filter    | FME过滤下增益  | FME低增益系数       |
| lo_fmx_filter    | FMX过滤下增益  | FMX低增益系数       |
| lo_lockon_filter | 下锁定增益     | 锁定加权温度计算的小系数   |
| lockon           | 温度带锁定锁定限制 | 温度带区锁定极限值      |
| min_cover_down   | 最小覆盖数     | 保温罩投用判断条件      |
| pu_dist_err      | 长度错误比例    | 前馈计算停止判断条件     |
| restart_delay    | 重启延迟      | 参考温度计算的判断条件    |
| slope_limit      | 温度斜率限制    | 温度斜率合法的判断条件    |
| smp_gauge        | 样本厚度      | 厚度分档           |
| smp_length       | 样本长度      | 长度分档           |
| spy_err_marg     | 喷淋失配补偿    | 单位流量偏差的判断条件    |
| spy_sts_err_pu   | 喷雾失配单位阈值  | 喷雾变化的判断条件      |
| tail_trim        | 尾倾度       | 头部开始位置         |
| temp_corr_db     | 温度修正死区    | 前馈温度控制的偏差的判断条件 |
| tmp_tol          | 温度公差      | 温度计算收敛判断条件     |
| turnoff_perm     | 喷淋关闭      | 允许喷淋不投用        |
| use_FME_pred     | 采用FME预报   | 采用FME预报温度标志位   |