## Video
https://youtu.be/7-zcO1BAFC0


## Mermaid Background
- [Docs](https://mermaid-js.github.io/mermaid/)
- [Live Editor](https://mermaid.live/)

## Mermaid Chart Source Code

```markdown
%% graph TD
flowchart TD
site((PrecisionDrilling.com))

host(WP Engine)
waf1(WP Engine)
waf2(Cloudflare)
dns(Azure DNS)
ns_registrar("Network Solutions (GoDaddy)")
cms(WordPress)
cms_login(/wp-admin/ OPEN)

site -- Hosted By --> host
site -- NS Registrar --> ns_registrar
site -- DNS Provider --> dns
site -- Protected By WAF1 --> waf1
site -- Protected By WAF2 --> waf2





rx("Recommendations (RX) & Vulnerabilities")

vuln1("XSS Injection on Site Search, unattackable - Low Risk")
rx1("Nothing IRL, WAF did its job.")
rx1_why("Could reduce OWASP! ZAP Alerts")

vuln2(WP Login Open - High Risk)
rx2("Lockdown /wp-admin/ by IP or HTTP User/Pass")
rx2_why(Prevent most junk login attempts, reduce log clutter)



site --> rx

vuln1 -- Blocked By Cloudflare --> waf2

rx --> vuln1
vuln1 -- RX --> rx1
rx1 -- Why? --> rx1_why

rx --> vuln2
vuln2 -- RX --> rx2
rx2 -- Why? --> rx2_why


site --> cms
cms --> cms_login
cms_login --> vuln2


dns_target("CNAME m6blypcji6rh.wpeproxy.com.")
dns --> dns_target
dns_target --> host

%% %% %%
%% cloudflare
%% %% %%
cloudflare_why("&quot;WP Engine recommends Cloudflare when configuring DNS because...&quot; ")
cloudflare_why_src("https://wpengine.com/support/cloudflare-best-practices/")

cloudflare_why --> cloudflare_why_src

waf2 --> cloudflare_why

host --> waf2


%% %% %%
%% Scans Done
%% %% %%

scans("Scans Performed")
scan1(OWASP! ZAP)
scan2(Burp)
scan3(wpsec.com)

site --> scans
scans --> scan1
scans --> scan2
scans --> scan3

%% ("https://wpsec.com/scan/?id=1eb9f5e51054e231071c4cb745ab1413")




```


## Gist URL to Source Code

Gist created with vscode plugin [GistPad](https://marketplace.visualstudio.com/items?itemName=vsls-contrib.gistfs)


> [!LINK] Gist Source for `markdown.live`
> https://gist.githubusercontent.com/GregSweats/bada1bb2512a581ce71cfaad82f907a6/raw/411be26f9ca328fcd832424a697db3854ab56694/pd-1.mermaid
> - for loading into [mermaid.live](https://mermaid.live/)

> [!LINK] View Gist on GitHub
> https://gist.github.com/GregSweats/bada1bb2512a581ce71cfaad82f907a6#file-pd-1-mermaid
>
> - Chart is rendered by GitHub b/c [apparently Mermaid Charts are supported by GitHub](https://github.blog/2022-02-14-include-diagrams-markdown-files-mermaid/)?
> 



## Rendered Chart with Mermaid Live Editor

[![](https://mermaid.ink/img/pako:eNp9VQtv2zYQ_is3AS0UwI9KSVrUw1o4dbYEyBzDyuZgMGDQ1NliLJEaScX2iv73HmXJtuxggAhIx-_uvnvqu8dVjF7Pe_cOlprlCTwNpnoqF6la84RpW30bYdH3Rxq5MELJgRZpKuSyw1V2ceEA7iTKWH8yglu5FBJL8ZotgnNR6H9LVREvUqZ3slgav_9foREGw6iUSDPTuBTGaqb9qTdEu1Z6BZFKC0sEDPh_qAGL4-3F1CsVeGb8idIxcTSmlsxSRX797jpvszgTsguPo9vhnrCLCtptuCPiGMPNlj6-gAvj-HYYwbimUgKOuR0DiTuMtHoVMe6AFNbxPd1Z5JWnSf_3oAS5FP0fKqxRYU379OgNZWiMVIsMZcyq_IyfL-A9_F2kEjWbi1RYgaZKljuvdBOQ4nMUwb18IZekB_REjkiETPOkBYVk1jK-YvOU2MGDWsNYmFVlR2-chaGyCTUD3I8fWo4xxCIGYQ28qHnngJytky2hv6kijUFjXHCEx0k_Gv0C__RH0E9R21OCoWueB1dEeMxREoM7sUxKCpXZkEw-KL6K1VrCUaHnW7gfgdJw9_Q0gr8M6u6IGbOnE5Z0qFteUVrIqObwUsgVlB0DFDRmuTWtmiiJgVPvWdQXp_mvKvcF9KaRXFfNm5S47Wp56PmziupNKSq1Gurj58pwUCXRCSfJ9mstdlG8YSXcJ7BhJaxiP7ESHltpREQzVI1S_bkbqcZ8Nb3Wh5p_ZpleonVFH_b_vIXs4zzd5vxFfNRJZ51jrtVm63ZI3SWkUw9Opdu01JhPd2htlU_1zvcpPr083FRt-P7fQtlf96uJ6lzNjzku1DqhpuNKLsSy0K7H3YzPkbPCYKfT2RmBegU1fMyM5uQnsTY3vS51JpaOXLhdU-S50rZ70GjP0dh2rhmNIUfTPZqDptldHc481WDXVW9Ajlf0m_vkJJERZ1SKgZJniSzbw91SbDvUCPVC6QzjirO7DfzDZO-FoX9T6Hz_eemvc4O8_IecNV7pYu9rLwrOReG56PIoqkYJKnddB-p-FfFvAc4_L67xOvhwfYXhZfDhU8Cv-PzT1TWbB1fBJYXktbwMdcZETL_J71MJVG6bYIZTr0evMdO0DafyB-GKnLYv3sbCKu31Fiw12PJYYVW0ldzrWV1gDRoIRv_brEL9-AnkCJXt)](https://mermaid.live/edit#pako:eNp9VQtv2zYQ_is3AS0UwI9KSVrUw1o4dbYEyBzDyuZgMGDQ1NliLJEaScX2iv73HmXJtuxggAhIx-_uvnvqu8dVjF7Pe_cOlprlCTwNpnoqF6la84RpW30bYdH3Rxq5MELJgRZpKuSyw1V2ceEA7iTKWH8yglu5FBJL8ZotgnNR6H9LVREvUqZ3slgav_9foREGw6iUSDPTuBTGaqb9qTdEu1Z6BZFKC0sEDPh_qAGL4-3F1CsVeGb8idIxcTSmlsxSRX797jpvszgTsguPo9vhnrCLCtptuCPiGMPNlj6-gAvj-HYYwbimUgKOuR0DiTuMtHoVMe6AFNbxPd1Z5JWnSf_3oAS5FP0fKqxRYU379OgNZWiMVIsMZcyq_IyfL-A9_F2kEjWbi1RYgaZKljuvdBOQ4nMUwb18IZekB_REjkiETPOkBYVk1jK-YvOU2MGDWsNYmFVlR2-chaGyCTUD3I8fWo4xxCIGYQ28qHnngJytky2hv6kijUFjXHCEx0k_Gv0C__RH0E9R21OCoWueB1dEeMxREoM7sUxKCpXZkEw-KL6K1VrCUaHnW7gfgdJw9_Q0gr8M6u6IGbOnE5Z0qFteUVrIqObwUsgVlB0DFDRmuTWtmiiJgVPvWdQXp_mvKvcF9KaRXFfNm5S47Wp56PmziupNKSq1Gurj58pwUCXRCSfJ9mstdlG8YSXcJ7BhJaxiP7ESHltpREQzVI1S_bkbqcZ8Nb3Wh5p_ZpleonVFH_b_vIXs4zzd5vxFfNRJZ51jrtVm63ZI3SWkUw9Opdu01JhPd2htlU_1zvcpPr083FRt-P7fQtlf96uJ6lzNjzku1DqhpuNKLsSy0K7H3YzPkbPCYKfT2RmBegU1fMyM5uQnsTY3vS51JpaOXLhdU-S50rZ70GjP0dh2rhmNIUfTPZqDptldHc481WDXVW9Ajlf0m_vkJJERZ1SKgZJniSzbw91SbDvUCPVC6QzjirO7DfzDZO-FoX9T6Hz_eemvc4O8_IecNV7pYu9rLwrOReG56PIoqkYJKnddB-p-FfFvAc4_L67xOvhwfYXhZfDhU8Cv-PzT1TWbB1fBJYXktbwMdcZETL_J71MJVG6bYIZTr0evMdO0DafyB-GKnLYv3sbCKu31Fiw12PJYYVW0ldzrWV1gDRoIRv_brEL9-AnkCJXt)


### Live Editor URL (Play with Themes)

>[!LINK] Edit Chart w/ Mermaid.live
> https://mermaid.live/edit?gist=https://gist.github.com/GregSweats/bada1bb2512a581ce71cfaad82f907a6#pako:eNpVU2FP2zAQ_SsnS6uYRNtpH6sBAsKACbEJOk0TQZMbXxMPx4589krV8t93dpIx8sk-v-f37p2zE5VTKBai9rJrYFmUFvg7fbhxUmlbw_e7G1hLbVDN4AdCJS0Ev4XgYK3r6BFcDLBptrNHmE6P9wWm--DL_dfbPZwdfDMoiVkNVk8QGl45S85g4hNiLiUsSKsAvXceFAaWo9n73slZuhbOd9f0Cq6c91iFk5cecp6VfyLtoRgVz41mxQZ9lrqTmmtsXRNFBG2h1qGJq9mnlZ8fX9vKxNxsUlh594QWjLZPCZhKPStjYaONAeoQFcQun67182i2d3Lr9nCxK7QCci06O1AJuceti0zSlO8fG7h4beDzwynlpNo-IqZkcs9L-bWdwYCZ__g_PaleZtWErVy3HRy_ofE4R9XLnOyQ25tSKW4dLA5KsYergyVPO9KYzlK3yNKcqlyleK40BecHqbV3LZBsc4gbQp-tROKsuJnKowz9yJWW_N7aMbYqD6uAxuMaStGE0NFiPh9mxN7nLfpWajX9Tf-WRv_BKSrN8vM8IJpb3JxIIl1bRDqaGLlCQ0erWE8Ccv-snja_PHbOh1mrJkEHg0dneeLvPn5ImZaCHfTvJd9aCnEoBk3-TXbJcSnSgPhowUslPZNK-8K42CkWucimxCL4iIdCxuDut7Ya9z2m6BPoiy9_AcpoLrg

## Contact Author
Greg Stevens, Dalyle DevOps Inc.
- (403) 213-5644 (best) 
- (403) 498-6809 (mobile) 
- greg@dalyle.ca (mainly unchecked) 
- www.dalyle.ca 
- www.stevens.pro

