# ds-whale-send-button 馃悑

鎶?DeepSeek Harness Web 瀵硅瘽杈撳叆鏍忕殑**涓诲彂閫佹寜閽浘鏍?*鏇挎崲涓?**DeepSeek 瀹樻柟椴搁奔 logo**銆?
- 涓嶆敼鍙戦€佽涓猴紝鍙崲鍥炬爣澶栬
- CSS `mask` 鍙犲姞瀹樻柟椴搁奔鍥惧舰锛岄鑹茶窡闅忔寜閽枃瀛楄壊锛坄currentColor`锛夛紝**浜壊/鏆楄壊涓婚鑷€傚簲**
- 涓嶈浼ゅ仠姝㈡寜閽€侀槦鍒楁寜閽瓑鍏跺畠鍥炬爣
- 绾祻瑙堝櫒绔牱寮忚鐩栵紝闆朵緷璧?
## 鏁堟灉

| 鐘舵€?| 鍥炬爣 |
|---|---|
| 杈撳叆鍐呭锛堟縺娲绘€侊級 | 馃悑 鐧借壊/浜壊椴搁奔 |
| 绌鸿緭鍏ワ紙绂佺敤鎬侊級 | 鐏拌壊椴搁奔 |
| 杩愯涓紙鍋滄鎸夐挳锛?| 淇濇寔鍘熸柟鍧楀浘鏍囷紙涓嶅彈褰卞搷锛?|

## 瀹夎

### 鏂瑰紡涓€锛氭湰鍦板寘瀹夎锛堝綋鍓嶇幆澧冨凡鐢級

```bash
# 鍦?web profile 涓嬪畨瑁咃紙鏈川 pnpm add锛屼細鍐欒繘 dsh.profile.bundles锛?dsh plugin --profile web add <璺緞>/dsh-external-ds-whale-send-button-0.1.0.tgz

# 楠岃瘉閰嶇疆鍙粍鍚?dsh --profile web --dump-config

# 閲嶅惎鏈嶅姟鐢熸晥
```

### 鏂瑰紡浜岋細鍔ㄦ€佹彃浠讹紙涓存椂锛岄噸鍚嵆涓級

鍦ㄣ€屽垱閫犳ā寮忋€嶄細璇濅腑鐢?`cordis_define` 瀹氫箟 `lib/client.js` 鐨勬彃浠跺璞″苟 `cordis_run`銆?
## 鍗歌浇

```bash
dsh plugin --profile web remove @dsh-external/ds-whale-send-button
```

## 宸ヤ綔鍘熺悊

鎻掍欢娉ㄥ唽涓?browser roster 鐨?client 鍖咃紙`dsh.client` 瀛楁 + `exports ./client`锛夛紝
`apply(ctx)` 鏃跺悜 `document.head` 娉ㄥ叆涓€娈?`<style>`锛堝甫 `data-plugin-css` 鏍囩锛屽箓绛夛級锛?
1. 鐢?`[data-composer-card]` + 鍙戦€佺澶?path 鐨勫敮涓€ `d` 鍓嶇紑绮剧‘瀹氫綅涓诲彂閫佹寜閽紱
2. 闅愯棌鍘熶笂浼犵澶?SVG锛?3. 鐢?CSS `mask` 鍙犲姞 DeepSeek 瀹樻柟椴搁奔锛堝彇鑷?dsh 鑷甫 `favicon.svg` 鐨勫畼鏂硅矾寰勶級锛?   `background-color: currentColor` 璁╅哺楸奸鑹查殢鎸夐挳鏂囧瓧鑹插彉鍖栥€?
## 鏂囦欢缁撴瀯

```
ds-whale-send-button/
鈹溾攢鈹€ package.json          # dsh.client + dsh.bundle.patch 澹版槑
鈹溾攢鈹€ cordis.patch.yml      # roster 娉ㄥ唽琛岋紙bundle patch 鑷姩鍙犲姞锛?鈹溾攢鈹€ lib/
鈹?  鈹溾攢鈹€ client.js         # 娴忚鍣ㄧ鎻掍欢锛堟牱寮忔敞鍏ワ級
鈹?  鈹斺攢鈹€ index.js          # host 鍗婄鍗犱綅
鈹斺攢鈹€ dsh-external-ds-whale-send-button-0.1.0.tgz  # npm pack 浜х墿
```

## 鑷畾涔?
鏀?`lib/client.js` 閲岀殑锛?
- `width/height: 16px` 鈫?鍥炬爣澶у皬
- `background-color: currentColor` 鈫?鍥哄畾棰滆壊锛堝 DeepSeek 钃?`#4D6BFE`锛?- `mask ... contain` 鈫?鍥炬爣缂╂斁鏂瑰紡

鏀瑰畬閲嶆柊 `npm pack` 骞剁敤 `dsh plugin --profile web add` 鍗囩骇銆?
## License

[MIT](./LICENSE)
