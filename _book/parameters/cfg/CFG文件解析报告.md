##                                 CFG文件解析报告

-  class = Adaptation

```c++
- [ ] thickness vernier calcs parameters
      thk_vern_enabled = true;    ![-]   Thickness vernier enabled
//厚度偏差修正模式开启
      thk_err_cl       = 0.03;    ! [mm] Thickness Error Clamp for vernier calcs
//厚度偏差取值范围0.03mm
      thk_vern_cl      = 0.010;   ! [mm] Thickness Vern  Clamp for verniercalcs
//厚度偏差计算范围0.01mm
     thk_prp_gain     = 0.300;   ! [-]  Thickness Vern Proportional Gain
//厚度偏差局部增益值
     thk_int_gain     = 0.150;   ! [-]  Thickness Vernier Integral Gain
//厚度偏差整体增益值

- [ ]  temperature vernier calcs parameters
        tmp_vern_enabled = false;   ! [-]   Temperature vernier enabled
//温度偏差修正模式关闭
        tmp_vern_gain    = 0.100;   ! [-]  Temperature vernier Gain
//温度偏差增益值
        tmp_err_cl       = 10.0;    ! [degC]  Temperature Error Clamp for vernier calcs
//温度偏差取值范围
        tmp_vern_cl      = 30.0;    ! [degC]  Temperature Vern  Clamp forvernier calcs
//温度自学习值计算范围

- [ ]   spy_effm_enabled = false;   ! [-]ispy spy eff modifier update enabled
//喷淋修正模式关闭
        spy_effm_gain    = 0.3;     ! [-] ispy spy eff modifier gain
//喷淋修正增益系数
        spy_effm_lo_lim  = 0.50;    ! [-] ispy spy eff modifier low limit
//喷淋修正最小值
        spy_effm_hi_lim  = 1.40;    ! [-] ispy spy eff modifier high limit
//喷淋修正最大值
        hd_bdy_tmp_fac     = 1.0;    ! [-][1.0=head] head and body temperature prop factor
//头部及中部入口温度自学习系数
```

-  class = cDraft

  ```c++
   dmode = dm_force; ! draft by per unit of force as default
  //单位轧制力计算压下量模式
          alpha          = 0.75;     ! ratio low limit clamp  = ( 1 - alpha )
  //注释？
          damp_mpy       = 0.75;     ! damping factor multiplier, to get critically damped convergence
  //衰减系数
          conv_crit       = 0.01;     ! convergence criterion on loading
  //载荷收敛标准
          max_dft_iter    = 50;       ! maximum iterations for draft loop
  //压下量最大迭代次数
          max_dftlim_iter = 100;      ! maximum iterations for draft limit resolution
  //压下量限制最大迭代次数
          dft_crit        = 0.01;     ! convergence criterion on resolving draft limits
  //压下量收敛标准
          frc_crit        = 0.01;     ! convergence criterion on resolving force limits
  //轧制力收敛标准
          pwr_crit        = 0.01;     ! convergence criterion on resolving power limits
  //功率收敛标准
          trq_crit        = 0.01;     ! convergence criterion on resolving torque limits
  //扭矩收敛标准
          thrdpwr_crit    = 0.10;     ! max thrd speed adjustment to remove thrd pwr lmt
  //最大穿带速度修正量
          flr_load        = 0.0;      ! extra load required to roll floor plate product 
  //轧制花纹板的额外负荷
          flrpudmin       = 0.135;    ! Desired pudraft required for floor plate
  //轧制花纹板的理想单位压下量
          max_dummy_passes   = 3;     ! Maximum number of dummy passes allowed.
  //空过道次
          fst_dummy_adjacent = 2;     ! Maximum number of adjacent dummy passes from F1
  //F1机架的最大相邻空过机架数
          lst_dummy_adjacent = 3;     ! Maximum number of adjacent dummy passes from Last stand
  //F7机架的最大相邻空过机架数
          !dmode_auto      = true;    ! allow auto selection of drafting mode
  //自动选择压下模式？
          !thick_pwr       = 3.1;     ! maximum aim PDI thickness for power mode
  //power mode下的最大目标厚度

    - [ ]   for Draft-Temperature calculation
          c_num_zlkfixed   = 6;       ! Max number of Zlk fixed in draft-temperature iterations
  //压下量-温度迭代最大ZLK修正次数
          ! for FRDM
          c_num_nrmethod = 10;        ! Maximum NR-method number
  //NR-method最大次数
          c_frdm_conv    = 0.005;     ! FRDM convergence condition
  //FRDM收敛条件
          c_num_zlkread  = 3;         ! Zlk read number in FRDM iterations
  //FRDM迭代时Zlk读取的数
          c_num_lmtchkmax = 4;        ! Limit check max times
  //限制条件检查最大次数
          c_num_lmtstdmax = 2;        ! Limit stand max number
  //限制机架最大数
          c_dlt_rfr       = 0.02;     ! Delta roll force ratio for coefficient
  //单位轧制力率
          c_num_lmtfrdm   = 2;        ! FRDM loop number in limit check calculation
  //在限制检查时，FRDM循环次数
          c_spdcone_mgn   = 0.88;     ! Speed cone limit margin
  //速度锥限制边界
  ```


```c++
 
```

-  class = cFeedback

```c
 pu_spy_tol        = 10.0;    ! [%]   spy flow tolerance to declare spray mismatch
 //喷淋水允许波动偏差百分比值
 min_lpr_pos       = 6,       ! [deg] min lpr angle to enable feedback calcs
            0.0, 0.0, 0.0, 0.0, 0.0, 0.1;
//允许反馈计算的最小活套角度
        thick_tol         = 0.500;   ! [mm]  thickness tolerance setup-measured
//设定—测量厚度偏差容忍度
        wid_tol           = 100.0;   ! [mm]  width tolerance setup-measured
//设定—测量宽度偏差容忍度
        tmp_tol           = 100.0;   ! [degC]   temperature tolerance setup-measured
//设定—测量温度偏差容忍度
        fdt_terr_lu       = 70.0;    ! [deg_F]  FDT upper temperature error to be used
//FDT上限偏差
        fdt_terr_ll       =-70.0;    ! [deg_F]  FDT lower temperature error to be used
//FDT下限偏差
        dfrc_tol          = 5000;    ! [kN] differential force tolerance
//两侧轧制力偏差容忍度
        frc_tol           = 0.75;    ! [-]   force tolerance setup-measured
//设定—测量轧制力偏差容忍度
        spd_tol           = 0.500;   ! [-]   speed tolerance setup-measured
//设定—测量速度偏差容忍
!!      thk_hd_fact       = 1.0;     ! [-]   thickness hd and very hd prop factor
//注释：？
        tmp_cnvg_tol      = 1.0;     ! [degC]   temperature loop convergence tolerance
//温度循环收敛条件
        max_tmp_iter      = 20;      ! [-]   maximum number of iterations for temp calcs
//温度计算最大迭代次数
        spy_eff_mod_min   = 0.75;    ! [-]   Spray efficiency modifier (calculated minimum)
//喷淋水修改的最小值
        spy_eff_mod_max   = 1.25;    ! [-]   Spray efficinecy modifier (calculated maximum)
//喷淋水修改的最大值
        min_force         = 100.0;   ! [-]   minimum force reqd to detect dummy stand
//检测空过机架的最小轧制力
        ztmp_log_enable   = true;
//注释：？ 
        shadow_mode       = false;   ! [-]   Shadow mode indicator
//注释：影子模式开启？
        ds_spy_calcs_enabled = 4,    ! [-]   Descalse sprays avaliable for adaptation
                true, true, true, true;
        is_spy_calcs_enabled = 6,    ! [-]   Interstand sprays avaliable for adaptation
                true, true, true, true, true, true;
        rgl_flw_est       = 10;      ! [ml/min] RGL establishment flow
//辊缝润滑设定流量
        massflow_iter     = 10;      ! [-]   loop num for massflow thickness calculation
//秒流量厚度计算的循环次数
        spy_mismatch_enable = false; ! [-]   Flag of spray mismatch enable
//喷淋水是否匹配标志
```

- class = cFTVD

```c
 create_object;
        objname    = ftvd;
        parentname = mill;
    end;
        crop_length     = 0.0;      ! [m] Typical head crop length
//切头剪头部剪切长度
        min_run_spd     = 1.0;      ! [m/sec] Minimum mill delivery speed
//最小机架出口速度
        max_run_spd     = 15.0;     ! [m/sec] Maximum mill delivery speed
//最大机架出口速度
        acc_m           = 0.0;      ! [m/sec/s] acceleration rate of M stand
//M机架的加速度
        acc_cs_tables   = 0.0;      ! [m/sec/s] acceleration rate of crop shear tables
//切头剪辊道的加速度
        dist_ds_m       = 0.000;    ! [m] distance M stand descaler entry to M stand(*)
//入口除鳞到M机架的距离
        dist_m_csentry  = 0.000;    ! [m] distance M stand to crop shear entry(*)
//切头剪入口到M机架的距离
        dist_cse_csx    = 0.000;    ! [m] distance crop shear entry to crop shear exit(*)
//切头剪入口到出口的距离
        dist_csx_f1     = 0.000;    ! [m] distance crop shear exit to f1 stand(*)
//切头剪出口到F1的距离
        thd_adj         = 1.0;      ! [-] thread adjustment tuning parameter
//穿带调整协调系数？
```

- class = cFZTerm

  1.  ZLK - Deformation resistance model learning

     ```c++
     cFZTerm = zlk1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             //自学习类型为乘法形式
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             //自学习方式为长期自学习
             cnt_max          = 1;     ![-] Maximum number for executing lot to lot learning
             //长期自学习执行的最大数量
         end;

         cFZTerm = zlk2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 1;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlk3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 1;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlk4;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 1;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlk5;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 1;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlk6;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 1;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlk7;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 1;     ![-] Maximum number for executing lot to lot learning
         end;
     ```

     ​

  2. ZLPH-Roll force model learning (Thickness)

     ```c
      cFZTerm = zlph1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             //自学习类型为乘法类型
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             //自学习方式为长期自学习
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
             //长期自学习执行最大数量为3
         end;

         cFZTerm = zlph2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlph3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlph4;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlph5;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlph6;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlph7;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

     ```

     ​

  3. ZBP-Roll force model learning

     ```c
      cFZTerm = zbp1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             //自学习类型为乘法类型
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             //自学习方式为短期自学习
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
             //长期自学习执行最大数量，因为是短期自学习，故为0
         end;

         cFZTerm = zbp2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbp3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbp4;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbp5;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbp6;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbp7;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
     ```

     ​

  4. ZBP-Roll force model furnace devision learning

     ```c
      cFZTerm = zbpfce1_1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             //自学习类型为乘法类型
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             //自学习方式为短期自学习
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce1_2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce1_3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce2_1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce2_2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce2_3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce3_1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce3_2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce3_3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce4_1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce4_2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce4_3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce5_1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce5_2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce5_3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce6_1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce6_2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce6_3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce7_1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce7_2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
         cFZTerm = zbpfce7_3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

     ```

     ​

  5.  ZLGH-Roll torque model learning (Thickness)

     ```c
       cFZTerm = zlgh1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             //自学习类型为乘法类型
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             //自学习方式为长期自学习
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
             //长期自学习最大执行数量为3
         end;

         cFZTerm = zlgh2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlgh3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlgh4;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlgh5;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlgh6;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zlgh7;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
         end;


     ```

     ​

  6.  ZBGRoll-torque model learning

     ```c
      cFZTerm = zbg1;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbg2;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbg3;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbg4;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbg5;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbg6;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbg7;
             z_type           = 1;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
     ```

     ​

  7.  ZBS - Gaugemeter thickness model learning at Head

     ```c
      cFZTerm = zbshd1;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             //自学习类型为加法
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             //自学习方式为短期自学习
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbshd2;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbshd3;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbshd4;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbshd5;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbshd6;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbshd7;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end；
     ```

     ​

  8. ZBS - Gaugemeter thickness model learning at Tail

     ```c
       cFZTerm = zbstl1;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             //加法
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             //短期
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbstl2;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbstl3;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbstl4;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbstl5;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbstl6;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;

         cFZTerm = zbstl7;
             z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
             z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
             cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
         end;
     ```

     ​

  9. ZBS-Gaugemeter thickness model cycle top learning

     ```c
       cFZTerm = zbscyc1;
             cnt_max          = 3;     ![-] Maximum number for executing cycle top learning
             //执行cycle自学习最大执行数量？
         end;

         cFZTerm = zbscyc2;
             cnt_max          = 3;     ![-] Maximum number for executing cycle top learning
         end;

         cFZTerm = zbscyc3;
             cnt_max          = 3;     ![-] Maximum number for executing cycle top learning
         end;

         cFZTerm = zbscyc4;
             cnt_max          = 3;     ![-] Maximum number for executing cycle top learning
         end;

         cFZTerm = zbscyc5;
             cnt_max          = 3;     ![-] Maximum number for executing cycle top learning
         end;

         cFZTerm = zbscyc6;
             cnt_max          = 3;     ![-] Maximum number for executing cycle top learning
         end;

         cFZTerm = zbscyc7;
             cnt_max          = 3;     ![-] Maximum number for executing cycle top learning
         end;
     ```

     ​

  10. ZLTCH-FM zone temperature correction

      ```c
      cFZTerm = zltch1;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              //加法
              z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              //长期
              cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
              //最大为3
          end;

          cFZTerm = zltch2;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zltch3;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zltch4;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zltch5;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zltch6;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zltch7;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 1;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 3;     ![-] Maximum number for executing lot to lot learning
          end;
      ```

      ​

  11. ZBTC-FM zone temperature correction

      ```c
         cFZTerm = zbtc1;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              //加法
              z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              //短期
              cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zbtc2;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zbtc3;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zbtc4;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zbtc5;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zbtc6;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
          end;

          cFZTerm = zbtc7;
              z_type           = 2;     ![-] Learning type. mulitiplicative type / additive type
              z_kind           = 2;     ![-] Learning kind. Lot to lot learning  / Bar to bar learning
              cnt_max          = 0;     ![-] Maximum number for executing lot to lot learning
          end;
      end;
      ```

  - class = cSetup

```c
 create_object;
        objname    = setup;
        parentname = mill;
    end;

    cSetup = setup;
        ssu_load_enab= false;       ! SSU model load distribution permissive
//不允许板形模型修改压下负荷
        dtloop_lmt   = 10;          ! draft-temperature iterations max limit
//压下量—温度迭代最大限制次数
        dtsloop_lmt  = 2;           ! draft-temperature-shape iterations max limit
//压下量—温度—板形迭代最大限制次数
        clr_ys_mult  = 0.8;         ! Coiler YS multiplier
//钢卷YS 系数？
        fat_mea_pass = 3;           ! FAT Measurement Pass Number
//FAT测量机架数？
        fat_gain     = 0.3;         ! FAT Gain for Level-1
//FAT增益？
!!      reset_thk_vern = true;      ! Reset thickness verniers after roll change
//换辊后厚度偏差清零
        reset_tmp_vern = true;      ! Reset temperature verniers after roll change
//换辊后温度偏差清零
        frdmloop_lmt   = 2;         ! FRDM iterations max limit
//FRDM最大迭代限制
        lltc_std_num   = 8;         ! Number of LLTC calculate stands
//LLTC计算的机架数
        n_scan         = 10;        ![-]   Number of scan
//扫描点数
        t_scan         = 0.2;       ![sec] Scan sampling pitch
//扫描的时间间隔
        sim_max_spd    = 13.0;      ![mps] Maximum speed when simulation
//模拟时的最大速度
    end;
end；
```

- class=ctemperature

  ```c
  class = cTemperature;
      create_object;
          objname    = temperature;
          parentname = mill;
      end;

      cTemperature = temperature;
          tmp_tol          = 2.0;      ![degC] target temperature prediction closure tolerance
            //目标温度预测中止偏差
          is_override_perm = false;    ![-] Spray pattern override is permitted if true
            //不允许改变除鳞模式
          turnoff_perm     = false;    ![-] Spray turn off is permitted if true even with
                                       !    non-zero pattern minimum flow
            //该项若为true，喷淋水流量为非零模式下的最小水流量
          use_FME_pred     = true;     ! Use predicted FME temperature when true
            //使用预计算的精轧入口温度
          dtmp_alt_thick   = 500.0;    ![degC] dTmp error to call for alternate thickness
            //厚度调整所需温度差值
          num_step         = 5;        !
            //？
          fmePyro_Name     = "fepyro"; ! FME pyrometer name
          //精轧入口温度名字为“fepyro”
          fmxPyro_Name     = "fxpyro"; ! FMX pyrometer name
          //精轧出口温度名字为“fxpyro”
          fmxTempTgt_Name  = "fxpyro"; ! Name of object whose exit piece is the target location
          //出口位置为目标区域的object的名字
          FMEDSTable_Name  = "f1etbl"; ! First descale spray table
          //精轧一次除鳞辊道
      end;
  end;
  ```

  ​