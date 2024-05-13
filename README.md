# RSS-GPT

[![](https://img.shields.io/github/last-commit/yinan-c/RSS-GPT/main?label=feeds%20refreshed)](https://yinan-c.github.io/RSS-GPT/)
[![](https://img.shields.io/github/license/yinan-c/RSS-GPT)](https://github.com/yinan-c/RSS-GPT/blob/master/LICENSE)


## What is this?

[Configuration Guide](https://yinan-c.github.io/rss-gpt-manual-en.html) | [中文简介](README-zh.md) | [中文教程](https://yinan-c.github.io/rss-gpt-manual-zh.html)

Using GitHub Actions to run a simple Python script repeatedly: Calling OpenAI API to generate summaries for RSS feeds, and push the generated feeds to GitHub Pages. Easy to configure, no server needed.

### Features

- Use ChatGPT to summarize RSS feeds, and attach summaries to the original articles, support custom summary length and target language.
- Aggregate multiple RSS feeds into one, remove duplicate articles, subscribe with a single address.
- Add filters to your own personalized RSS feeds.
- Host your own RSS feeds on GitHub repo and GitHub Pages.

![](https://i.imgur.com/7darABv.jpg)

## Quick configuration guide

- Fork this repo
- Add Repository Secrets
    - U_NAME: your GitHub username
    - U_EMAIL: your GitHub email
    - WORK_TOKEN: your GitHub personal accesstoken with `repo` and `workflow` scope, get it from [GitHub settings](https://github.com/settings/tokens/new)
    - OPENAI_API_KEY(OPTIONAL, only needed when using AI summarization feature): Get it from [OpenAI website](https://platform.openai.com/account/api-keys)
- Enable GitHub Pages in repo settings, choose deploy from branch, and set the directory to `/docs`.
- Configure your RSS feeds in config.ini

You can check out [here](https://yinan-c.github.io/rss-gpt-manual-en.html) for a more detailed configuration guide.

## ChangeLog and updates

- As OpenAI released a new version of `openai` package on Nov 06, 2023.  [More powerful models are coming](https://openai.com/blog/new-models-and-developer-products-announced-at-devday), the way to call API also changed. As a result, the old script will no longer work with the latest version installed, and needs to be updated. Otherwise, you will have to set `openai==0.27.8` in `requirements.txt` to use the old version.
-  In the latest updates, **contexts longer than 16k tokens are no longer truncated, instead, will use the `gpt-4-1106-preview` model.** If you don't like this, let me know and I'll think about adding customizability to choose whether truncate or use `gpt-4-1106-preview` model.
- Check out the [CHANGELOG.md](CHANGELOG.md).

### Contributions are welcome!

- Feel free to submit issues and pull requests.

## Support this project

- If you find it helpful, please star this repo. Please also consider buying me a coffee to help maintain this project and cover the expenses of OpenAI API while hosting the feeds. I appreciate your support.

<a href="https://www.buymeacoffee.com/yinan" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

## Example feeds being processed

These feeds on hosted in the [`docs/` subdirectory](https://github.com/yinan-c/RSS-GPT/tree/main/docs) in this repo as well as on my [GitHub Pages](https://yinan-c.github.io/RSS-GPT/). Feel free to subscribe in your favorite RSS reader.

I will consider hosting more feeds in the future. Email me or submit an issue if there are any questions using the script or any suggestions.

- http://tw.wleilei.com:1200/zhihu/topic/19758322 -> https://wllwang8.github.io/RSS-GPT/zhihu-meirijingxuan.xml
- http://tw.wleilei.com:1200/zhihu/daily -> https://wllwang8.github.io/RSS-GPT/zhihu-daily.xml
- http://tw.wleilei.com:1200/zhihu/people/activities/vaxin -> https://wllwang8.github.io/RSS-GPT/fanxin.xml
- http://tw.wleilei.com:1200/zhihu/people/activities/li-bo-jie -> https://wllwang8.github.io/RSS-GPT/li-bo-jie.xml
- http://tw.wleilei.com:1200/zhihu/people/activities/datalearner -> https://wllwang8.github.io/RSS-GPT/datalearner.xml
- https://www.zhihu.com/people/mli65 -> https://wllwang8.github.io/RSS-GPT/limu.xml
- http://tw.wleilei.com:1200/zhihu/posts/org/xin-zhi-yuan-88-3 -> https://wllwang8.github.io/RSS-GPT/xin-zhi-yuan.xml
- http://tw.wleilei.com:1200/zhihu/posts/org/liang-zi-wei-48 -> https://wllwang8.github.io/RSS-GPT/liang-zi-wei.xml
- http://tw.wleilei.com:1200/zhihu/posts/org/ji-qi-zhi-xin-65 -> https://wllwang8.github.io/RSS-GPT/ji-qi-zhi-xin.xml
- http://tw.wleilei.com:1200/zhihu/people/activities/wu-en-da-89 -> https://wllwang8.github.io/RSS-GPT/wu-en-da.xml
- http://tw.wleilei.com:1200/zhihu/people/activities/chen-feng-40-67-10 -> https://wllwang8.github.io/RSS-GPT/chen-feng.xml
- http://tw.wleilei.com:1200/zhihu/people/activities/yu-yun-angelia -> https://wllwang8.github.io/RSS-GPT/yu-yun-angelia.xml
- http://tw.wleilei.com:1200/zhihu/people/activities/heda-he-28 -> https://wllwang8.github.io/RSS-GPT/qiang-hua-xue-tu.xml
- http://tw.wleilei.com:1200/zhihu/zhuanlan/paperweekly -> https://wllwang8.github.io/RSS-GPT/PaperWeekly.xml
- http://tw.wleilei.com:4001/feeds/MP_WXS_3883824137 -> https://wllwang8.github.io/RSS-GPT/liu-run.xml
- http://tw.wleilei.com:4001/feeds/MP_WXS_3089330056 -> https://wllwang8.github.io/RSS-GPT/zhang-li-jun.xml
- http://tw.wleilei.com:4001/feeds/MP_WXS_3566232719 -> https://wllwang8.github.io/RSS-GPT/xie-yan.xml
- http://tw.wleilei.com:4001/feeds/MP_WXS_2398933301 -> https://wllwang8.github.io/RSS-GPT/ai-nlp.xml
- http://tw.wleilei.com:4001/feeds/MP_WXS_3226363426 -> https://wllwang8.github.io/RSS-GPT/Datawhale.xml
- http://tw.wleilei.com:8090/i/?a=normal&get=f_3 -> https://wllwang8.github.io/RSS-GPT/weng-lilian.xml
- http://tw.wleilei.com:8090/i/?a=normal&get=f_2 -> https://wllwang8.github.io/RSS-GPT/bangxian-w.xml
- https://feeds.feedburner.com/ruanyifeng -> https://wllwang8.github.io/RSS-GPT/ruanyifeng.xml
