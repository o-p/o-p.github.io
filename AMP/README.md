# AMP ⚡ Accelerated Mobile Pages Project

- 加速手機體驗的規格
    - HTML 本身就包含幾乎所有的排版資訊, 不需要等待載入外部 stylesheet 才能正常顯示, 也不會在載入 stylesheet 後重新排版造成效能損耗
    - 符合規格的 AMP HTML, 會被轉換成壓縮版本的網頁, 放到 AMP CDN 上, 讓其他分享平台快速載入
    
- HTML mock up 基本規範直接看 [template](https://github.com/o-p/o-p.github.io/blob/master/AMP/template.html)

- 後台透過 [AMP API](https://developers.google.com/amp/cache/overview) 可以得到 AMP 處理過的 CDN PATH
    - 每次可查詢 50 筆
    - 優先使用 `cdnAmpUrl`
    - 目前看來, CDN版本只是將html minify, 沒有更多的處理 (例如將amp-img 換成不同元件)
    - example json response:
        ```json
{
     "ampUrls": [
          {
               "originalUrl": "http://o-p.github.io/AMP/template.html",
               "ampUrl": "http://o-p.github.io/AMP/template.html",
               "cdnAmpUrl": "https://o--p-github-io.cdn.ampproject.org/c/o-p.github.io/AMP/template.html"
          }
     ]
}
 
        ```
    
