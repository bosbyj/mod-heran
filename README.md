# mod-heran mod鹤然

## 下载魔然简体版
https://github.com/ksqsf/rime-moran
最新action里面，找到artifact

## fixed码表准备

文件 `moran_fixed_simp.dict.yaml`

1码2码简码
参考小鹤官方简码，2简词位，换成高频单字，zy=尊，ty=吞
https://github.com/zodensu/FlyPY-zodensu
https://zhuanlan.zhihu.com/p/556027991

3码简码 【最后只用这个，实现语句流畅输入】
参考 zrm2000.dict.yaml 已经按词频排序
https://github.com/vitszeng/rime-zrm2000
用脚本转换成小鹤双拼

4码全码
参考 moran.chars.dict.yaml 按词频过滤
用脚本转换成小鹤双拼

## schema编辑algebra

文件 `moran.yaml`

```
  # 用戶自定義演算式，這部分演算式會注入到類整句方案的開頭和結尾，不包括字詞模式
  # 用例：實現模糊音、將自然碼雙拼映射爲別的雙拼方案等
  user_sentence_top:
    __append:
      - xform/^([a-z]+);/\U$1;/   # 雙拼編碼轉大寫以避免衝突，如 vd;yd -> VD;yd

      # ...下面需要一一把自然碼雙拼替換成小鶴雙拼【这里！】
      - xform/^IB/iz/
      - xform/^CB/cz/
      - xform/^DB/dz/
      - xform/^FB/fz/
      - xform/^GB/gz/
      - xform/^HB/hz/
      - xform/^KB/kz/
      - xform/^LB/lz/
      - xform/^MB/mz/
      - xform/^NB/nz/
      - xform/^PB/pz/
      - xform/^RB/rz/
      - xform/^UB/uz/
      - xform/^SB/sz/
      - xform/^TB/tz/
      - xform/^YB/yz/
      - xform/^VB/vz/
      - xform/^ZB/zz/
      - xform/^BC/bn/
      - xform/^DC/dn/
      - xform/^JC/jn/
      - xform/^LC/ln/
      - xform/^MC/mn/
      - xform/^NC/nn/
      - xform/^PC/pn/
      - xform/^QC/qn/
      - xform/^TC/tn/
      - xform/^XC/xn/
      - xform/^DD/dl/
      - xform/^JD/jl/
      - xform/^LD/ll/
      - xform/^ND/nl/
      - xform/^QD/ql/
      - xform/^XD/xl/
      - xform/^ID/il/
      - xform/^GD/gl/
      - xform/^HD/hl/
      - xform/^KD/kl/
      - xform/^UD/ul/
      - xform/^VD/vl/
      - xform/^BK/bc/
      - xform/^CK/cc/
      - xform/^IK/ic/
      - xform/^DK/dc/
      - xform/^GK/gc/
      - xform/^HK/hc/
      - xform/^KK/kc/
      - xform/^LK/lc/
      - xform/^MK/mc/
      - xform/^NK/nc/
      - xform/^PK/pc/
      - xform/^RK/rc/
      - xform/^SK/sc/
      - xform/^UK/uc/
      - xform/^TK/tc/
      - xform/^YK/yc/
      - xform/^ZK/zc/
      - xform/^VK/vc/
      - xform/^BL/bd/
      - xform/^CL/cd/
      - xform/^IL/id/
      - xform/^DL/dd/
      - xform/^GL/gd/
      - xform/^HL/hd/
      - xform/^KL/kd/
      - xform/^LL/ld/
      - xform/^ML/md/
      - xform/^NL/nd/
      - xform/^PL/pd/
      - xform/^SL/sd/
      - xform/^UL/ud/
      - xform/^TL/td/
      - xform/^WL/wd/
      - xform/^ZL/zd/
      - xform/^VL/vd/
      - xform/^BN/bb/
      - xform/^JN/jb/
      - xform/^LN/lb/
      - xform/^MN/mb/
      - xform/^NN/nb/
      - xform/^PN/pb/
      - xform/^QN/qb/
      - xform/^XN/xb/
      - xform/^YN/yb/
      - xform/^IP/iy/
      - xform/^CP/cy/
      - xform/^DP/dy/
      - xform/^GP/gy/
      - xform/^HP/hy/
      - xform/^JP/jy/
      - xform/^KP/ky/
      - xform/^LP/ly/
      - xform/^NP/ny/
      - xform/^QP/qy/
      - xform/^RP/ry/
      - xform/^UP/uy/
      - xform/^SP/sy/
      - xform/^TP/ty/
      - xform/^XP/xy/
      - xform/^YP/yy/
      - xform/^VP/vy/
      - xform/^ZP/zy/
      - xform/^JW/jx/
      - xform/^LW/lx/
      - xform/^NW/nx/
      - xform/^QW/qx/
      - xform/^XW/xx/
      - xform/^IW/ix/
      - xform/^GW/gx/
      - xform/^HW/hx/
      - xform/^KW/kx/
      - xform/^UW/ux/
      - xform/^VW/vx/
      - xform/^BX/bp/
      - xform/^DX/dp/
      - xform/^JX/jp/
      - xform/^LX/lp/
      - xform/^MX/mp/
      - xform/^NX/np/
      - xform/^PX/pp/
      - xform/^QX/qp/
      - xform/^TX/tp/
      - xform/^XX/xp/
      - xform/^BY/bk/
      - xform/^DY/dk/
      - xform/^JY/jk/
      - xform/^LY/lk/
      - xform/^MY/mk/
      - xform/^NY/nk/
      - xform/^PY/pk/
      - xform/^QY/qk/
      - xform/^TY/tk/
      - xform/^XY/xk/
      - xform/^YY/yk/
      - xform/^IY/ik/
      - xform/^GY/gk/
      - xform/^HY/hk/
      - xform/^KY/kk/
      - xform/^UY/uk/
      - xform/^VY/vk/
      - xform/^BZ/bw/
      - xform/^DZ/dw/
      - xform/^FZ/fw/
      - xform/^GZ/gw/
      - xform/^HZ/hw/
      - xform/^KZ/kw/
      - xform/^LZ/lw/
      - xform/^MZ/mw/
      - xform/^NZ/nw/
      - xform/^PZ/pw/
      - xform/^SZ/sw/
      - xform/^UZ/uw/
      - xform/^TZ/tw/
      - xform/^WZ/ww/
      - xform/^ZZ/zw/
      - xform/^VZ/vw/

      - xlit/ABCDEFGHIJKLMNOPQRSTUVWXYZ/abcdefghijklmnopqrstuvwxyz/  # 大寫轉回小寫
    #   __patch:
    #     - moran_defs:/bufen/z_zh
    #     - moran_defs:/bufen/c_ch
    #     - moran_defs:/bufen/s_sh
    #     - moran_defs:/bufen/en_eng
```

## 参考讨论

自定義雙拼方案
https://github.com/ksqsf/rime-moran/issues/41

优化码表的原则
https://github.com/ksqsf/rime-moran/issues/43#issuecomment-2053551470
