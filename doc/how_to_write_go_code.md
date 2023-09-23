





<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
  <link rel="dns-prefetch" href="https://assets-cdn.github.com">
  <link rel="dns-prefetch" href="https://avatars0.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars1.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars2.githubusercontent.com">
  <link rel="dns-prefetch" href="https://avatars3.githubusercontent.com">
  <link rel="dns-prefetch" href="https://github-cloud.s3.amazonaws.com">
  <link rel="dns-prefetch" href="https://user-images.githubusercontent.com/">



  <link crossorigin="anonymous" media="all" integrity="sha512-Z0JAar9+DkI1NjGVdZr3GivARUgJtA0o2eHlTv7Ou2gshR5awWVf8QGsq11Ns9ZxQLEs+G5/SuARmvpOLMzulw==" rel="stylesheet" href="https://assets-cdn.github.com/assets/frameworks-95aff0b550d3fe338b645a4deebdcb1b.css" />
  <link crossorigin="anonymous" media="all" integrity="sha512-eeb0wTQqP0vhEg0FWGwR3lZqg7k8NoNJ3aJm5fyWM7vaSlm1ZgpLpIlXr0J82rnhHRYlpkDX1w034JzTj9YfJQ==" rel="stylesheet" href="https://assets-cdn.github.com/assets/github-1b92fc57a93ac751f875b024fc0646d2.css" />
  
  
  <link crossorigin="anonymous" media="all" integrity="sha512-2ThuYzT4A4rqWiPrSjHGQiV5pWat6IhKBOQbt3SI++BucjSUbJlzSD2S9h0pM5UHlP1KpvSk9YtKp0JinP+yVQ==" rel="stylesheet" href="https://assets-cdn.github.com/assets/site-2dc8680244624c331677d1cfd1af7370.css" />
  

  <meta name="viewport" content="width=device-width">
  
  <title>golang-tutorial/how_to_write_go_code.md at master · Tinywan/golang-tutorial · GitHub</title>
    <meta name="description" content=":bouquet: Golang 系列教程(译). Contribute to Tinywan/golang-tutorial development by creating an account on GitHub.">
    <link rel="search" type="application/opensearchdescription+xml" href="/opensearch.xml" title="GitHub">
  <link rel="fluid-icon" href="https://github.com/fluidicon.png" title="GitHub">
  <meta property="fb:app_id" content="1401488693436528">

    
    <meta property="og:image" content="https://avatars0.githubusercontent.com/u/14959876?s=400&amp;v=4" /><meta property="og:site_name" content="GitHub" /><meta property="og:type" content="object" /><meta property="og:title" content="Tinywan/golang-tutorial" /><meta property="og:url" content="https://github.com/Tinywan/golang-tutorial" /><meta property="og:description" content=":bouquet: Golang 系列教程(译). Contribute to Tinywan/golang-tutorial development by creating an account on GitHub." />

  <link rel="assets" href="https://assets-cdn.github.com/">
  
  <meta name="pjax-timeout" content="1000">
  
  <meta name="request-id" content="9216:2266:7636A4:A3ED7D:5B8BF32A" data-pjax-transient>


  

  <meta name="selected-link" value="repo_source" data-pjax-transient>

      <meta name="google-site-verification" content="KT5gs8h0wvaagLKAVWq8bbeNwnZZK1r1XQysX3xurLU">
    <meta name="google-site-verification" content="ZzhVyEFwb7w3e0-uOTltm8Jsck2F5StVihD0exw2fsA">
    <meta name="google-site-verification" content="GXs5KoUUkNCoaAZn7wPN-t01Pywp9M3sEjnt_3_ZWPc">

  <meta name="octolytics-host" content="collector.githubapp.com" /><meta name="octolytics-app-id" content="github" /><meta name="octolytics-event-url" content="https://collector.githubapp.com/github-external/browser_event" /><meta name="octolytics-dimension-request_id" content="9216:2266:7636A4:A3ED7D:5B8BF32A" /><meta name="octolytics-dimension-region_edge" content="ap-southeast-1" /><meta name="octolytics-dimension-region_render" content="iad" />
<meta name="analytics-location" content="/&lt;user-name&gt;/&lt;repo-name&gt;/blob/show" data-pjax-transient="true" />



    <meta name="google-analytics" content="UA-3769691-2">


<meta class="js-ga-set" name="dimension1" content="Logged Out">



  

      <meta name="hostname" content="github.com">
    <meta name="user-login" content="">

      <meta name="expected-hostname" content="github.com">
    <meta name="js-proxy-site-detection-payload" content="ODhlNWRhNjZkYjUyZTA3ZGZlYjViMWJjMWFmZThmMTkwZGRmMTk0ZTMzNmQ0M2NlNzViMmYxMzE5MmY2M2M4NHx7InJlbW90ZV9hZGRyZXNzIjoiMTE2LjYuOTkuMjIwIiwicmVxdWVzdF9pZCI6IjkyMTY6MjI2Njo3NjM2QTQ6QTNFRDdEOjVCOEJGMzJBIiwidGltZXN0YW1wIjoxNTM1ODk4NDExLCJob3N0IjoiZ2l0aHViLmNvbSJ9">

    <meta name="enabled-features" content="DASHBOARD_V2_LAYOUT_OPT_IN,EXPLORE_DISCOVER_REPOSITORIES,UNIVERSE_BANNER,FREE_TRIALS,MARKETPLACE_INSIGHTS,MARKETPLACE_PLAN_RESTRICTION_EDITOR,MARKETPLACE_SEARCH,MARKETPLACE_INSIGHTS_CONVERSION_PERCENTAGES">

  <meta name="html-safe-nonce" content="8c5a8e283bdb124600e629c4fe9a52ac267a760c">

  <meta http-equiv="x-pjax-version" content="047ccdd462e94f60c49cd5a457fc731b">
  

      <link href="https://github.com/Tinywan/golang-tutorial/commits/master.atom" rel="alternate" title="Recent Commits to golang-tutorial:master" type="application/atom+xml">

  <meta name="go-import" content="github.com/Tinywan/golang-tutorial git https://github.com/Tinywan/golang-tutorial.git">

  <meta name="octolytics-dimension-user_id" content="14959876" /><meta name="octolytics-dimension-user_login" content="Tinywan" /><meta name="octolytics-dimension-repository_id" content="125475660" /><meta name="octolytics-dimension-repository_nwo" content="Tinywan/golang-tutorial" /><meta name="octolytics-dimension-repository_public" content="true" /><meta name="octolytics-dimension-repository_is_fork" content="false" /><meta name="octolytics-dimension-repository_network_root_id" content="125475660" /><meta name="octolytics-dimension-repository_network_root_nwo" content="Tinywan/golang-tutorial" /><meta name="octolytics-dimension-repository_explore_github_marketplace_ci_cta_shown" content="false" />


    <link rel="canonical" href="https://github.com/Tinywan/golang-tutorial/blob/master/docs/how_to_write_go_code.md" data-pjax-transient>


  <meta name="browser-stats-url" content="https://api.github.com/_private/browser/stats">

  <meta name="browser-errors-url" content="https://api.github.com/_private/browser/errors">

  <link rel="mask-icon" href="https://assets-cdn.github.com/pinned-octocat.svg" color="#000000">
  <link rel="icon" type="image/x-icon" class="js-site-favicon" href="https://assets-cdn.github.com/favicon.ico">

<meta name="theme-color" content="#1e2327">



  <link rel="manifest" href="/manifest.json" crossOrigin="use-credentials">

  </head>

  <body class="logged-out env-production page-blob">
    

  <div class="position-relative js-header-wrapper ">
    <a href="#start-of-content" tabindex="1" class="px-2 py-4 bg-blue text-white show-on-focus js-skip-to-content">Skip to content</a>
    <div id="js-pjax-loader-bar" class="pjax-loader-bar"><div class="progress"></div></div>

    
    
    



        


  <header class="Header header-logged-out  position-relative f4 py-3" role="banner" data-ga-load="(Logged out) Header, view, experiment:site_header_dropdowns; group:control">
    <div class="container-lg d-flex px-3">
      <div class="d-flex flex-justify-between flex-items-center">
        <a class="header-logo-invertocat my-0" href="https://github.com/" aria-label="Homepage" data-ga-click="(Logged out) Header, go to homepage, icon:logo-wordmark; experiment:site_header_dropdowns; group:control">
          <svg height="32" class="octicon octicon-mark-github" viewBox="0 0 16 16" version="1.1" width="32" aria-hidden="true"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"/></svg>
        </a>

      </div>

      <div class="HeaderMenu d-flex flex-justify-between flex-auto">
          <nav class="mt-0">
            <ul class="d-flex list-style-none">
                <li class="ml-2">
                  <a class="js-selected-navigation-item HeaderNavlink px-0 py-2 m-0" data-ga-click="Header, click, Nav menu - item:features; experiment:site_header_dropdowns; group:control" data-selected-links="/features /features/project-management /features/code-review /features/project-management /features/integrations /features" href="/features">
                    Features
</a>                </li>
                <li class="ml-4">
                  <a class="js-selected-navigation-item HeaderNavlink px-0 py-2 m-0" data-ga-click="Header, click, Nav menu - item:business; experiment:site_header_dropdowns; group:control" data-selected-links="/business /business/security /business/customers /business" href="/business">
                    Business
</a>                </li>

                <li class="ml-4">
                  <a class="js-selected-navigation-item HeaderNavlink px-0 py-2 m-0" data-ga-click="Header, click, Nav menu - item:explore; experiment:site_header_dropdowns; group:control" data-selected-links="/explore /trending /trending/developers /integrations /integrations/feature/code /integrations/feature/collaborate /integrations/feature/ship showcases showcases_search showcases_landing /explore" href="/explore">
                    Explore
</a>                </li>

                <li class="ml-4">
                      <a class="js-selected-navigation-item HeaderNavlink px-0 py-2 m-0" data-ga-click="Header, click, Nav menu - item:marketplace; experiment:site_header_dropdowns; group:control" data-selected-links=" /marketplace" href="/marketplace">
                        Marketplace
</a>                </li>
                <li class="ml-4">
                  <a class="js-selected-navigation-item HeaderNavlink px-0 py-2 m-0" data-ga-click="Header, click, Nav menu - item:pricing; experiment:site_header_dropdowns; group:control" data-selected-links="/pricing /pricing/developer /pricing/team /pricing/business-hosted /pricing/business-enterprise /pricing" href="/pricing">
                    Pricing
</a>                </li>
            </ul>
          </nav>

        <div class="d-flex">
            <div class="d-lg-flex flex-items-center mr-3">
              <div class="header-search scoped-search site-scoped-search js-site-search position-relative js-jump-to"
  role="search combobox"
  aria-owns="jump-to-results"
  aria-label="Search or jump to"
  aria-haspopup="listbox"
  aria-expanded="true"
>
  <div class="position-relative">
    <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="js-site-search-form" data-scope-type="Repository" data-scope-id="125475660" data-scoped-search-url="/Tinywan/golang-tutorial/search" data-unscoped-search-url="/search" action="/Tinywan/golang-tutorial/search" accept-charset="UTF-8" method="get"><input name="utf8" type="hidden" value="&#x2713;" />
      <label class="form-control header-search-wrapper header-search-wrapper-jump-to position-relative d-flex flex-justify-between flex-items-center js-chromeless-input-container">
        <input type="text"
          class="form-control header-search-input jump-to-field js-jump-to-field js-site-search-focus js-site-search-field is-clearable"
          data-hotkey="s,/"
          name="q"
          value=""
          placeholder="Search"
          data-unscoped-placeholder="Search GitHub"
          data-scoped-placeholder="Search"
          autocapitalize="off"
          aria-autocomplete="list"
          aria-controls="jump-to-results"
          data-jump-to-suggestions-path="/_graphql/GetSuggestedNavigationDestinations#csrf-token=gzNJ35SYDOw2jKr1T1VmQ3t1Hf0Kt79rVFVdopeBg4ZJ8EToqvCIZulqsKxrco0psFfFIUQSJbcX3RiRSpxnqg=="
          spellcheck="false"
          autocomplete="off"
          >
          <input type="hidden" class="js-site-search-type-field" name="type" >
            <img src="https://assets-cdn.github.com/images/search-shortcut-hint.svg" alt="" class="mr-2 header-search-key-slash">

            <div class="Box position-absolute overflow-hidden d-none jump-to-suggestions js-jump-to-suggestions-container">
              <ul class="d-none js-jump-to-suggestions-template-container">
                <li class="d-flex flex-justify-start flex-items-center p-0 f5 navigation-item js-navigation-item">
                  <a tabindex="-1" class="no-underline d-flex flex-auto flex-items-center p-2 jump-to-suggestions-path js-jump-to-suggestion-path js-navigation-open" href="">
                    <div class="jump-to-octicon js-jump-to-octicon mr-2 text-center d-none"></div>
                    <img class="avatar mr-2 flex-shrink-0 js-jump-to-suggestion-avatar" alt="" aria-label="Team" src="" width="28" height="28">

                    <div class="jump-to-suggestion-name js-jump-to-suggestion-name flex-auto overflow-hidden text-left no-wrap css-truncate css-truncate-target">
                    </div>

                    <div class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none js-jump-to-badge-search">
                      <span class="js-jump-to-badge-search-text-default d-none" aria-label="in this repository">
                        In this repository
                      </span>
                      <span class="js-jump-to-badge-search-text-global d-none" aria-label="in all of GitHub">
                        All GitHub
                      </span>
                      <span aria-hidden="true" class="d-inline-block ml-1 v-align-middle">↵</span>
                    </div>

                    <div aria-hidden="true" class="border rounded-1 flex-shrink-0 bg-gray px-1 text-gray-light ml-1 f6 d-none d-on-nav-focus js-jump-to-badge-jump">
                      Jump to
                      <span class="d-inline-block ml-1 v-align-middle">↵</span>
                    </div>
                  </a>
                </li>
                <svg height="16" width="16" class="octicon octicon-repo flex-shrink-0 js-jump-to-repo-octicon-template" title="Repository" aria-label="Repository" viewBox="0 0 12 16" version="1.1" role="img"><path fill-rule="evenodd" d="M4 9H3V8h1v1zm0-3H3v1h1V6zm0-2H3v1h1V4zm0-2H3v1h1V2zm8-1v12c0 .55-.45 1-1 1H6v2l-1.5-1.5L3 16v-2H1c-.55 0-1-.45-1-1V1c0-.55.45-1 1-1h10c.55 0 1 .45 1 1zm-1 10H1v2h2v-1h3v1h5v-2zm0-10H2v9h9V1z"/></svg>
                <svg height="16" width="16" class="octicon octicon-project flex-shrink-0 js-jump-to-project-octicon-template" title="Project" aria-label="Project" viewBox="0 0 15 16" version="1.1" role="img"><path fill-rule="evenodd" d="M10 12h3V2h-3v10zm-4-2h3V2H6v8zm-4 4h3V2H2v12zm-1 1h13V1H1v14zM14 0H1a1 1 0 0 0-1 1v14a1 1 0 0 0 1 1h13a1 1 0 0 0 1-1V1a1 1 0 0 0-1-1z"/></svg>
                <svg height="16" width="16" class="octicon octicon-search flex-shrink-0 js-jump-to-search-octicon-template" title="Search" aria-label="Search" viewBox="0 0 16 16" version="1.1" role="img"><path fill-rule="evenodd" d="M15.7 13.3l-3.81-3.83A5.93 5.93 0 0 0 13 6c0-3.31-2.69-6-6-6S1 2.69 1 6s2.69 6 6 6c1.3 0 2.48-.41 3.47-1.11l3.83 3.81c.19.2.45.3.7.3.25 0 .52-.09.7-.3a.996.996 0 0 0 0-1.41v.01zM7 10.7c-2.59 0-4.7-2.11-4.7-4.7 0-2.59 2.11-4.7 4.7-4.7 2.59 0 4.7 2.11 4.7 4.7 0 2.59-2.11 4.7-4.7 4.7z"/></svg>
              </ul>
              <ul class="d-none js-jump-to-no-results-template-container">
                <li class="d-flex flex-justify-center flex-items-center p-3 f5 d-none">
                  <span class="text-gray">No suggested jump to results</span>
                </li>
              </ul>

              <ul id="jump-to-results" class="js-navigation-container jump-to-suggestions-results-container js-jump-to-suggestions-results-container" >
                <li class="d-flex flex-justify-center flex-items-center p-0 f5">
                  <img src="https://assets-cdn.github.com/images/spinners/octocat-spinner-128.gif" alt="Octocat Spinner Icon" class="m-2" width="28">
                </li>
              </ul>
            </div>
      </label>
</form>  </div>
</div>

            </div>

          <span class="d-inline-block">
              <div class="HeaderNavlink px-0 py-2 m-0">
                <a class="text-bold text-white no-underline" href="/login?return_to=%2FTinywan%2Fgolang-tutorial%2Fblob%2Fmaster%2Fdocs%2Fhow_to_write_go_code.md" data-ga-click="(Logged out) Header, clicked Sign in, text:sign-in; experiment:site_header_dropdowns; group:control">Sign in</a>
                  <span class="text-gray">or</span>
                  <a class="text-bold text-white no-underline" href="/join?source=experiment-header-control-repo" data-ga-click="(Logged out) Header, clicked Sign up, text:sign-up; experiment:site_header_dropdowns; group:control">Sign up</a>
              </div>
          </span>
        </div>
      </div>
    </div>
  </header>

  </div>

  <div id="start-of-content" class="show-on-focus"></div>

    <div id="js-flash-container">


</div>



  <div role="main" class="application-main ">
        <div itemscope itemtype="http://schema.org/SoftwareSourceCode" class="">
    <div id="js-repo-pjax-container" data-pjax-container >
      







  <div class="pagehead repohead instapaper_ignore readability-menu experiment-repo-nav  ">
    <div class="repohead-details-container clearfix container">

      <ul class="pagehead-actions">
  <li>
      <a href="/login?return_to=%2FTinywan%2Fgolang-tutorial"
    class="btn btn-sm btn-with-count tooltipped tooltipped-s"
    aria-label="You must be signed in to watch a repository" rel="nofollow">
    <svg class="octicon octicon-eye v-align-text-bottom" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M8.06 2C3 2 0 8 0 8s3 6 8.06 6C13 14 16 8 16 8s-3-6-7.94-6zM8 12c-2.2 0-4-1.78-4-4 0-2.2 1.8-4 4-4 2.22 0 4 1.8 4 4 0 2.22-1.78 4-4 4zm2-4c0 1.11-.89 2-2 2-1.11 0-2-.89-2-2 0-1.11.89-2 2-2 1.11 0 2 .89 2 2z"/></svg>
    Watch
  </a>
  <a class="social-count" href="/Tinywan/golang-tutorial/watchers"
     aria-label="15 users are watching this repository">
    15
  </a>

  </li>

  <li>
      <a href="/login?return_to=%2FTinywan%2Fgolang-tutorial"
    class="btn btn-sm btn-with-count tooltipped tooltipped-s"
    aria-label="You must be signed in to star a repository" rel="nofollow">
    <svg class="octicon octicon-star v-align-text-bottom" viewBox="0 0 14 16" version="1.1" width="14" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M14 6l-4.9-.64L7 1 4.9 5.36 0 6l3.6 3.26L2.67 14 7 11.67 11.33 14l-.93-4.74L14 6z"/></svg>
    Star
  </a>

    <a class="social-count js-social-count" href="/Tinywan/golang-tutorial/stargazers"
      aria-label="68 users starred this repository">
      68
    </a>

  </li>

  <li>
      <a href="/login?return_to=%2FTinywan%2Fgolang-tutorial"
        class="btn btn-sm btn-with-count tooltipped tooltipped-s"
        aria-label="You must be signed in to fork a repository" rel="nofollow">
        <svg class="octicon octicon-repo-forked v-align-text-bottom" viewBox="0 0 10 16" version="1.1" width="10" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M8 1a1.993 1.993 0 0 0-1 3.72V6L5 8 3 6V4.72A1.993 1.993 0 0 0 2 1a1.993 1.993 0 0 0-1 3.72V6.5l3 3v1.78A1.993 1.993 0 0 0 5 15a1.993 1.993 0 0 0 1-3.72V9.5l3-3V4.72A1.993 1.993 0 0 0 8 1zM2 4.2C1.34 4.2.8 3.65.8 3c0-.65.55-1.2 1.2-1.2.65 0 1.2.55 1.2 1.2 0 .65-.55 1.2-1.2 1.2zm3 10c-.66 0-1.2-.55-1.2-1.2 0-.65.55-1.2 1.2-1.2.65 0 1.2.55 1.2 1.2 0 .65-.55 1.2-1.2 1.2zm3-10c-.66 0-1.2-.55-1.2-1.2 0-.65.55-1.2 1.2-1.2.65 0 1.2.55 1.2 1.2 0 .65-.55 1.2-1.2 1.2z"/></svg>
        Fork
      </a>

    <a href="/Tinywan/golang-tutorial/network/members" class="social-count"
       aria-label="11 users forked this repository">
      11
    </a>
  </li>
</ul>

      <h1 class="public ">
  <svg class="octicon octicon-repo" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9H3V8h1v1zm0-3H3v1h1V6zm0-2H3v1h1V4zm0-2H3v1h1V2zm8-1v12c0 .55-.45 1-1 1H6v2l-1.5-1.5L3 16v-2H1c-.55 0-1-.45-1-1V1c0-.55.45-1 1-1h10c.55 0 1 .45 1 1zm-1 10H1v2h2v-1h3v1h5v-2zm0-10H2v9h9V1z"/></svg>
  <span class="author" itemprop="author"><a class="url fn" rel="author" href="/Tinywan">Tinywan</a></span><!--
--><span class="path-divider">/</span><!--
--><strong itemprop="name"><a data-pjax="#js-repo-pjax-container" href="/Tinywan/golang-tutorial">golang-tutorial</a></strong>

</h1>

    </div>
    
<nav class="reponav js-repo-nav js-sidenav-container-pjax container"
     itemscope
     itemtype="http://schema.org/BreadcrumbList"
     role="navigation"
     data-pjax="#js-repo-pjax-container">

  <span itemscope itemtype="http://schema.org/ListItem" itemprop="itemListElement">
    <a class="js-selected-navigation-item selected reponav-item" itemprop="url" data-hotkey="g c" data-selected-links="repo_source repo_downloads repo_commits repo_releases repo_tags repo_branches repo_packages /Tinywan/golang-tutorial" href="/Tinywan/golang-tutorial">
      <svg class="octicon octicon-code" viewBox="0 0 14 16" version="1.1" width="14" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M9.5 3L8 4.5 11.5 8 8 11.5 9.5 13 14 8 9.5 3zm-5 0L0 8l4.5 5L6 11.5 2.5 8 6 4.5 4.5 3z"/></svg>
      <span itemprop="name">Code</span>
      <meta itemprop="position" content="1">
</a>  </span>

    <span itemscope itemtype="http://schema.org/ListItem" itemprop="itemListElement">
      <a itemprop="url" data-hotkey="g i" class="js-selected-navigation-item reponav-item" data-selected-links="repo_issues repo_labels repo_milestones /Tinywan/golang-tutorial/issues" href="/Tinywan/golang-tutorial/issues">
        <svg class="octicon octicon-issue-opened" viewBox="0 0 14 16" version="1.1" width="14" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7 2.3c3.14 0 5.7 2.56 5.7 5.7s-2.56 5.7-5.7 5.7A5.71 5.71 0 0 1 1.3 8c0-3.14 2.56-5.7 5.7-5.7zM7 1C3.14 1 0 4.14 0 8s3.14 7 7 7 7-3.14 7-7-3.14-7-7-7zm1 3H6v5h2V4zm0 6H6v2h2v-2z"/></svg>
        <span itemprop="name">Issues</span>
        <span class="Counter">1</span>
        <meta itemprop="position" content="2">
</a>    </span>

  <span itemscope itemtype="http://schema.org/ListItem" itemprop="itemListElement">
    <a data-hotkey="g p" itemprop="url" class="js-selected-navigation-item reponav-item" data-selected-links="repo_pulls checks /Tinywan/golang-tutorial/pulls" href="/Tinywan/golang-tutorial/pulls">
      <svg class="octicon octicon-git-pull-request" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M11 11.28V5c-.03-.78-.34-1.47-.94-2.06C9.46 2.35 8.78 2.03 8 2H7V0L4 3l3 3V4h1c.27.02.48.11.69.31.21.2.3.42.31.69v6.28A1.993 1.993 0 0 0 10 15a1.993 1.993 0 0 0 1-3.72zm-1 2.92c-.66 0-1.2-.55-1.2-1.2 0-.65.55-1.2 1.2-1.2.65 0 1.2.55 1.2 1.2 0 .65-.55 1.2-1.2 1.2zM4 3c0-1.11-.89-2-2-2a1.993 1.993 0 0 0-1 3.72v6.56A1.993 1.993 0 0 0 2 15a1.993 1.993 0 0 0 1-3.72V4.72c.59-.34 1-.98 1-1.72zm-.8 10c0 .66-.55 1.2-1.2 1.2-.65 0-1.2-.55-1.2-1.2 0-.65.55-1.2 1.2-1.2.65 0 1.2.55 1.2 1.2zM2 4.2C1.34 4.2.8 3.65.8 3c0-.65.55-1.2 1.2-1.2.65 0 1.2.55 1.2 1.2 0 .65-.55 1.2-1.2 1.2z"/></svg>
      <span itemprop="name">Pull requests</span>
      <span class="Counter">0</span>
      <meta itemprop="position" content="3">
</a>  </span>

    <a data-hotkey="g b" class="js-selected-navigation-item reponav-item" data-selected-links="repo_projects new_repo_project repo_project /Tinywan/golang-tutorial/projects" href="/Tinywan/golang-tutorial/projects">
      <svg class="octicon octicon-project" viewBox="0 0 15 16" version="1.1" width="15" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M10 12h3V2h-3v10zm-4-2h3V2H6v8zm-4 4h3V2H2v12zm-1 1h13V1H1v14zM14 0H1a1 1 0 0 0-1 1v14a1 1 0 0 0 1 1h13a1 1 0 0 0 1-1V1a1 1 0 0 0-1-1z"/></svg>
      Projects
      <span class="Counter" >0</span>
</a>



  <a class="js-selected-navigation-item reponav-item" data-selected-links="repo_graphs repo_contributors dependency_graph pulse /Tinywan/golang-tutorial/pulse" href="/Tinywan/golang-tutorial/pulse">
    <svg class="octicon octicon-graph" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M16 14v1H0V0h1v14h15zM5 13H3V8h2v5zm4 0H7V3h2v10zm4 0h-2V6h2v7z"/></svg>
    Insights
</a>

</nav>


  </div>

<div class="container new-discussion-timeline experiment-repo-nav  ">
  <div class="repository-content ">

    
  <a class="d-none js-permalink-shortcut" data-hotkey="y" href="/Tinywan/golang-tutorial/blob/30b377189b56e52a90888af94718de000ddc1d14/docs/how_to_write_go_code.md">Permalink</a>

  <!-- blob contrib key: blob_contributors:v21:d285915a9ad6541e541eb0ff2b51e341 -->

      <div class="signup-prompt-bg rounded-1">
      <div class="signup-prompt p-4 text-center mb-4 rounded-1">
        <div class="position-relative">
          <!-- '"` --><!-- </textarea></xmp> --></option></form><form action="/site/dismiss_signup_prompt" accept-charset="UTF-8" method="post"><input name="utf8" type="hidden" value="&#x2713;" /><input type="hidden" name="authenticity_token" value="Oo7aUJXyFhy8/zYoU/c3bgrW9BeHlKriFeA50j7gNhhzFL5fmxI2ffg8nJ+E3LhPy3zZsf4sHgA7cqOtV5+XAw==" />
            <button type="submit" class="position-absolute top-0 right-0 btn-link link-gray" data-ga-click="(Logged out) Sign up prompt, clicked Dismiss, text:dismiss">
              Dismiss
            </button>
</form>          <h3 class="pt-2">Join GitHub today</h3>
          <p class="col-6 mx-auto">GitHub is home to over 28 million developers working together to host and review code, manage projects, and build software together.</p>
          <a class="btn btn-primary" href="/join?source=prompt-blob-show" data-ga-click="(Logged out) Sign up prompt, clicked Sign up, text:sign-up">Sign up</a>
        </div>
      </div>
    </div>


  <div class="file-navigation">
    
<div class="select-menu branch-select-menu js-menu-container js-select-menu float-left">
  <button class=" btn btn-sm select-menu-button js-menu-target css-truncate" data-hotkey="w"
    
    type="button" aria-label="Switch branches or tags" aria-expanded="false" aria-haspopup="true">
      <i>Branch:</i>
      <span class="js-select-button css-truncate-target">master</span>
  </button>

  <div class="select-menu-modal-holder js-menu-content js-navigation-container" data-pjax>

    <div class="select-menu-modal">
      <div class="select-menu-header">
        <svg class="octicon octicon-x js-menu-close" role="img" aria-label="Close" viewBox="0 0 12 16" version="1.1" width="12" height="16"><path fill-rule="evenodd" d="M7.48 8l3.75 3.75-1.48 1.48L6 9.48l-3.75 3.75-1.48-1.48L4.52 8 .77 4.25l1.48-1.48L6 6.52l3.75-3.75 1.48 1.48L7.48 8z"/></svg>
        <span class="select-menu-title">Switch branches/tags</span>
      </div>

      <div class="select-menu-filters">
        <div class="select-menu-text-filter">
          <input type="text" aria-label="Filter branches/tags" id="context-commitish-filter-field" class="form-control js-filterable-field js-navigation-enable" placeholder="Filter branches/tags">
        </div>
        <div class="select-menu-tabs">
          <ul>
            <li class="select-menu-tab">
              <a href="#" data-tab-filter="branches" data-filter-placeholder="Filter branches/tags" class="js-select-menu-tab" role="tab">Branches</a>
            </li>
            <li class="select-menu-tab">
              <a href="#" data-tab-filter="tags" data-filter-placeholder="Find a tag…" class="js-select-menu-tab" role="tab">Tags</a>
            </li>
          </ul>
        </div>
      </div>

      <div class="select-menu-list select-menu-tab-bucket js-select-menu-tab-bucket" data-tab-filter="branches" role="menu">

        <div data-filterable-for="context-commitish-filter-field" data-filterable-type="substring">


            <a class="select-menu-item js-navigation-item js-navigation-open selected"
               href="/Tinywan/golang-tutorial/blob/master/docs/how_to_write_go_code.md"
               data-name="master"
               data-skip-pjax="true"
               rel="nofollow">
              <svg class="octicon octicon-check select-menu-item-icon" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M12 5l-8 8-4-4 1.5-1.5L4 10l6.5-6.5L12 5z"/></svg>
              <span class="select-menu-item-text css-truncate-target js-select-menu-filter-text">
                master
              </span>
            </a>
            <a class="select-menu-item js-navigation-item js-navigation-open "
               href="/Tinywan/golang-tutorial/blob/revert-8-patch-4/docs/how_to_write_go_code.md"
               data-name="revert-8-patch-4"
               data-skip-pjax="true"
               rel="nofollow">
              <svg class="octicon octicon-check select-menu-item-icon" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M12 5l-8 8-4-4 1.5-1.5L4 10l6.5-6.5L12 5z"/></svg>
              <span class="select-menu-item-text css-truncate-target js-select-menu-filter-text">
                revert-8-patch-4
              </span>
            </a>
        </div>

          <div class="select-menu-no-results">Nothing to show</div>
      </div>

      <div class="select-menu-list select-menu-tab-bucket js-select-menu-tab-bucket" data-tab-filter="tags">
        <div data-filterable-for="context-commitish-filter-field" data-filterable-type="substring">


            <a class="select-menu-item js-navigation-item js-navigation-open "
              href="/Tinywan/golang-tutorial/tree/v2.0/docs/how_to_write_go_code.md"
              data-name="v2.0"
              data-skip-pjax="true"
              rel="nofollow">
              <svg class="octicon octicon-check select-menu-item-icon" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M12 5l-8 8-4-4 1.5-1.5L4 10l6.5-6.5L12 5z"/></svg>
              <span class="select-menu-item-text css-truncate-target" title="v2.0">
                v2.0
              </span>
            </a>
            <a class="select-menu-item js-navigation-item js-navigation-open "
              href="/Tinywan/golang-tutorial/tree/v1.0/docs/how_to_write_go_code.md"
              data-name="v1.0"
              data-skip-pjax="true"
              rel="nofollow">
              <svg class="octicon octicon-check select-menu-item-icon" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M12 5l-8 8-4-4 1.5-1.5L4 10l6.5-6.5L12 5z"/></svg>
              <span class="select-menu-item-text css-truncate-target" title="v1.0">
                v1.0
              </span>
            </a>
        </div>

        <div class="select-menu-no-results">Nothing to show</div>
      </div>

    </div>
  </div>
</div>

    <div class="BtnGroup float-right">
      <a href="/Tinywan/golang-tutorial/find/master"
            class="js-pjax-capture-input btn btn-sm BtnGroup-item"
            data-pjax
            data-hotkey="t">
        Find file
      </a>
      <clipboard-copy for="blob-path" class="btn btn-sm BtnGroup-item">
        Copy path
      </clipboard-copy>
    </div>
    <div id="blob-path" class="breadcrumb">
      <span class="repo-root js-repo-root"><span class="js-path-segment"><a data-pjax="true" href="/Tinywan/golang-tutorial"><span>golang-tutorial</span></a></span></span><span class="separator">/</span><span class="js-path-segment"><a data-pjax="true" href="/Tinywan/golang-tutorial/tree/master/docs"><span>docs</span></a></span><span class="separator">/</span><strong class="final-path">how_to_write_go_code.md</strong>
    </div>
  </div>


  <include-fragment src="/Tinywan/golang-tutorial/contributors/master/docs/how_to_write_go_code.md" class="commit-tease commit-loader">
    <div>
      Fetching contributors&hellip;
    </div>

    <div class="commit-tease-contributors">
        <img alt="" class="loader-loading float-left" src="https://assets-cdn.github.com/images/spinners/octocat-spinner-32-EAF2F5.gif" width="16" height="16" />
      <span class="loader-error">Cannot retrieve contributors at this time</span>
    </div>
</include-fragment>


  <div class="file">
    <div class="file-header">
  <div class="file-actions">

    <div class="BtnGroup">
      <a id="raw-url" class="btn btn-sm BtnGroup-item" href="/Tinywan/golang-tutorial/raw/master/docs/how_to_write_go_code.md">Raw</a>
        <a class="btn btn-sm js-update-url-with-hash BtnGroup-item" data-hotkey="b" href="/Tinywan/golang-tutorial/blame/master/docs/how_to_write_go_code.md">Blame</a>
      <a rel="nofollow" class="btn btn-sm BtnGroup-item" href="/Tinywan/golang-tutorial/commits/master/docs/how_to_write_go_code.md">History</a>
    </div>


        <button type="button" class="btn-octicon disabled tooltipped tooltipped-nw"
          aria-label="You must be signed in to make or propose changes">
          <svg class="octicon octicon-pencil" viewBox="0 0 14 16" version="1.1" width="14" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M0 12v3h3l8-8-3-3-8 8zm3 2H1v-2h1v1h1v1zm10.3-9.3L12 6 9 3l1.3-1.3a.996.996 0 0 1 1.41 0l1.59 1.59c.39.39.39 1.02 0 1.41z"/></svg>
        </button>
        <button type="button" class="btn-octicon btn-octicon-danger disabled tooltipped tooltipped-nw"
          aria-label="You must be signed in to make or propose changes">
          <svg class="octicon octicon-trashcan" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M11 2H9c0-.55-.45-1-1-1H5c-.55 0-1 .45-1 1H2c-.55 0-1 .45-1 1v1c0 .55.45 1 1 1v9c0 .55.45 1 1 1h7c.55 0 1-.45 1-1V5c.55 0 1-.45 1-1V3c0-.55-.45-1-1-1zm-1 12H3V5h1v8h1V5h1v8h1V5h1v8h1V5h1v9zm1-10H2V3h9v1z"/></svg>
        </button>
  </div>

  <div class="file-info">
      352 lines (259 sloc)
      <span class="file-info-divider"></span>
    11.4 KB
  </div>
</div>

    
  <div id="readme" class="readme blob instapaper_body">
    <article class="markdown-body entry-content" itemprop="text"><h1><a id="user-content-如何编写go代码" class="anchor" aria-hidden="true" href="#如何编写go代码"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>如何编写Go代码</h1>
<p>简介：介绍如何使用go命令获取、构建和安装包，命令和运行测试。</p>
<h2><a id="user-content-概述" class="anchor" aria-hidden="true" href="#概述"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>概述</h2>
<blockquote>
<p>目录</p>
</blockquote>
<ul>
<li>介绍</li>
<li>代码组织
<ul>
<li>概观</li>
<li>工作区</li>
<li>GOPATH环境变量</li>
<li>导入路径</li>
<li>你的第一个程序</li>
<li>你的第一个库</li>
</ul>
</li>
<li>包名称</li>
<li>测试</li>
<li>远程软件包</li>
</ul>
<blockquote>
<p>介绍</p>
</blockquote>
<p>本文档演示了一个简单Go包的开发过程，并介绍了go工具，这是获取、构建和安装Go包和命令的标准方法。</p>
<p>该go工具要求您以特定方式组织您的代码。</p>
<h2><a id="user-content-代码组织" class="anchor" aria-hidden="true" href="#代码组织"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M4 9h1v1H4c-1.5 0-3-1.69-3-3.5S2.55 3 4 3h4c1.45 0 3 1.69 3 3.5 0 1.41-.91 2.72-2 3.25V8.59c.58-.45 1-1.27 1-2.09C10 5.22 8.98 4 8 4H4c-.98 0-2 1.22-2 2.5S3 9 4 9zm9-3h-1v1h1c1 0 2 1.22 2 2.5S13.98 12 13 12H9c-.98 0-2-1.22-2-2.5 0-.83.42-1.64 1-2.09V6.25c-1.09.53-2 1.84-2 3.25C6 11.31 7.55 13 9 13h4c1.45 0 3-1.69 3-3.5S14.5 6 13 6z"></path></svg></a>代码组织</h2>
<blockquote>
<p>概观</p>
</blockquote>
<p>请注意，这与其他编程环境不同，在这些编程环境中，每个项目都有一个单独的工作区，工作区与版本控制存储库紧密相关。</p>
<ul>
<li>Go程序员通常将他们所有的Go代码保存在一个工作区中。</li>
<li>工作区包含许多版本控制存储库 （例如，由Git管理）。</li>
<li>每个存储库都包含一个或多个包。</li>
<li>每个软件包由一个目录中的一个或多个Go源文件组成。</li>
<li>包的目录的路径决定了它的导入路径。</li>
</ul>
<blockquote>
<p>工作区</p>
</blockquote>
<p>工作空间是一个目录层次结构，其根目录包含三个目录：</p>
<ul>
<li>src 包含Go源文件，</li>
<li>pkg 包含包对象</li>
<li>bin 包含可执行命令。</li>
</ul>
<p>该go工具构建源包并将生成的二进制文件安装到pkg和bin目录。</p>
<p>该<code>src</code>子目录通常包含多个版本控制存储库（例如Git或Mercurial），用于跟踪一个或多个源包的开发。</p>
<p>为了让您了解工作空间在实践中的外观，下面是一个例子：</p>
<div class="highlight highlight-source-go"><pre>bin/
    hello                          # 命令可执行文件
    outyet                         # 命令可执行文件
pkg/
    linux_amd64/
        github.<span class="pl-smi">com</span>/golang/example/
            stringutil.<span class="pl-smi">a</span>           # 包对象
src/
    github.<span class="pl-smi">com</span>/golang/example/
        .<span class="pl-smi">git</span>/                      # <span class="pl-v">Git</span>存储库元数据
	hello/
	    hello.<span class="pl-smi">go</span>               # 命令源
	outyet/
	    main.<span class="pl-smi">go</span>                # command source
	    main_test.<span class="pl-smi">go</span>           # test source
	stringutil/
	    reverse.<span class="pl-smi">go</span>             # 包源码
	    reverse_test.<span class="pl-smi">go</span>        # 测试源码
    golang.<span class="pl-smi">org</span>/x/image/
        .<span class="pl-smi">git</span>/                      # <span class="pl-v">Git</span>存储库元数据
	bmp/
	    reader.<span class="pl-smi">go</span>              # <span class="pl-k">package</span> source
	    writer.<span class="pl-smi">go</span>              # <span class="pl-k">package</span> source
    ... (many more repositories and packages omitted) ...</pre></div>
<p>上面的树显示了一个包含两个存储库（example和image）的工作空间。该example库包含两个命令（hello 和outyet）和一个库（<code>stringutil</code>）。该image存储库包含该bmp包和其他几个包。</p>
<p>典型的工作空间包含许多包含许多包和命令的源代码库。大多数Go程序员将他们所有的Go源代码和依赖关系保存在一个工作区中。</p>
<p>命令和库由不同类型的源代码包构建而成。</p>
<blockquote>
<p>第一个程序</p>
</blockquote>
<p>要编译并运行一个简单的程序，首先选择一个包路径（我们将使用 <code>github.com/user/hello</code>）并在工作区内创建一个相应的包目录：</p>
<div class="highlight highlight-source-shell"><pre>mkdir <span class="pl-smi">$GOPATH</span>/src/github.com/user/hello</pre></div>
<p>接下来，创建一个名为hello.go该目录内的文件，其中包含以下Go代码。</p>
<div class="highlight highlight-source-go"><pre><span class="pl-k">package</span> main

<span class="pl-k">import</span> <span class="pl-s"><span class="pl-pds">"</span>fmt<span class="pl-pds">"</span></span>

<span class="pl-k">func</span> <span class="pl-en">main</span>() {
	fmt.<span class="pl-c1">Printf</span>(<span class="pl-s"><span class="pl-pds">"</span>Hello, world.<span class="pl-cce">\n</span><span class="pl-pds">"</span></span>)
}</pre></div>
<p>现在，您可以使用该go工具构建和安装该程序</p>
<div class="highlight highlight-source-go"><pre>$ <span class="pl-k">go</span> install github.<span class="pl-smi">com</span>/user/hello <span class="pl-c"><span class="pl-c">//</span> 编译包文件并且编译整个程序</span></pre></div>
<p>请注意，您可以从系统上的任何位置运行此命令。该 go工具通过查找 <code>github.com/user/hello</code> 指定的工作区内的程序包来查找源代码 <code>GOPATH</code>。</p>
<p>如果<code>go install</code>从软件包目录运行，也可以省略软件包路径：</p>
<div class="highlight highlight-source-go"><pre>$ cd $GOPATH/src/github.<span class="pl-smi">com</span>/user/hello
$ <span class="pl-k">go</span> install</pre></div>
<p>该命令构建<code>hello</code>命令，生成可执行的二进制文件。然后它将该二进制文件安装到工作空间的<code>bin</code>目录<code>hello</code>（或者在Windows下<code>hello.exe</code>）。在我们的例子中，那将是<code>$GOPATH/bin/hello</code>，这是<code>$HOME/go/bin/hello</code>。</p>
<p>该<code>go</code>工具只会在发生错误时打印输出，因此如果这些命令不产生任何输出，它们将成功执行。</p>
<p>您现在可以通过在命令行键入完整路径来运行该程序：</p>
<div class="highlight highlight-source-shell"><pre>$ <span class="pl-smi">$GOPATH</span>/bin/hello
Hello, world.</pre></div>
<p>或者，如您添加<code>$GOPATH/bin</code>到您的<code>PATH</code>，只需键入二进制名称：</p>
<div class="highlight highlight-source-go"><pre>$ hello
Hello, world.</pre></div>
<p>如果您正在使用源代码管理系统，现在应该是初始化存储库，添加文件并提交第一个更改的好时机。再一次，这一步是可选的：你不需要使用源代码控制来编写Go代码。</p>
<div class="highlight highlight-source-shell"><pre>$ <span class="pl-c1">cd</span> <span class="pl-smi">$GOPATH</span>/src/github.com/user/hello
$ git init
Initialized empty Git repository <span class="pl-k">in</span> /home/user/work/src/github.com/user/hello/.git/
$ git add hello.go
$ git commit -m <span class="pl-s"><span class="pl-pds">"</span>initial commit<span class="pl-pds">"</span></span>
[master (root-commit) 0b4507d] initial commit
 1 file changed, 1 insertion(+)
  create mode 100644 hello.go
$ git remote add origin https://github.com/Tinywan/hello.git
$ git push -u origin master</pre></div>
<p>将代码推送到远程存储库作为自己的练习。</p>
<blockquote>
<p>你的第一库</p>
</blockquote>
<p>我们来编写一个库并从<code>hello</code>程序中使用它。</p>
<p>再次，第一步是选择一个包路径（我们将使用 <code>github.com/user/stringutil</code>）并创建包目录：</p>
<div class="highlight highlight-source-shell"><pre>$ mkdir <span class="pl-smi">$GOPATH</span>/src/github.com/user/stringutil</pre></div>
<p>接下来，使用以下内容创建一个名称在该目录中的文件。</p>
<div class="highlight highlight-source-go"><pre><span class="pl-c"><span class="pl-c">//</span> Package stringutil contains utility functions for working with strings.</span>
<span class="pl-k">package</span> stringutil

<span class="pl-c"><span class="pl-c">//</span> Reverse returns its argument string reversed rune-wise left to right.</span>
<span class="pl-k">func</span> <span class="pl-en">Reverse</span>(<span class="pl-v">s</span> <span class="pl-v">string</span>) <span class="pl-v">string</span> {
	<span class="pl-smi">r</span> <span class="pl-k">:=</span> []<span class="pl-c1">rune</span>(s)
	<span class="pl-k">for</span> <span class="pl-smi">i</span>, <span class="pl-smi">j</span> <span class="pl-k">:=</span> <span class="pl-c1">0</span>, <span class="pl-c1">len</span>(r)-<span class="pl-c1">1</span>; i &lt; <span class="pl-c1">len</span>(r)/<span class="pl-c1">2</span>; i, j = i+<span class="pl-c1">1</span>, j-<span class="pl-c1">1</span> {
		r[i], r[j] = r[j], r[i]
	}
	<span class="pl-k">return</span> <span class="pl-c1">string</span>(r)
}</pre></div>
<p>现在，测试该软件包是用下面用<code>go build</code>命令进行代码编译：</p>
<div class="highlight highlight-source-shell"><pre>$ go build github.com/user/stringutil  // 测试编译，检查编译是否有编译错误</pre></div>
<p>或者，如果您在包的源目录中工作，只需：</p>
<div class="highlight highlight-source-shell"><pre>$ go build </pre></div>
<p>这不会产生输出文件。为此，必须使用<code>go install</code>将包对象放置在工作空间的<code>pkg</code>目录中的方法。</p>
<p>确认stringutil软件包构建完成后，修改原始文件<code>hello.go</code>（位于 <code>$GOPATH/src/github.com/user/hello</code>）以使用它：</p>
<div class="highlight highlight-source-go"><pre><span class="pl-k">package</span> main

<span class="pl-k">import</span> (
	<span class="pl-s"><span class="pl-pds">"</span>fmt<span class="pl-pds">"</span></span>
	<span class="pl-s"><span class="pl-pds">"</span>github.com/user/stringutil<span class="pl-pds">"</span></span>
)

<span class="pl-k">func</span> <span class="pl-en">main</span>() {
	fmt.<span class="pl-c1">Printf</span>(stringutil.<span class="pl-c1">Reverse</span>(<span class="pl-s"><span class="pl-pds">"</span>!oG ,olleH<span class="pl-pds">"</span></span>))
}</pre></div>
<p>无论何时该go工具<strong>安装包或二进制文件</strong>，<strong>它也会安装它所具有的任何依赖关系</strong>。所以当你安装hello程序</p>
<div class="highlight highlight-source-shell"><pre>$ go install github.com/user/hello</pre></div>
<p>该<code>stringutil</code>包也将自动安装。</p>
<p>运行该程序的新版本，您应该看到一条新的反转消息：</p>
<div class="highlight highlight-source-shell"><pre>$ hello
Hello, Go<span class="pl-k">!</span></pre></div>
<p>完成上述步骤后，您的工作空间应如下所示：</p>
<div class="highlight highlight-source-shell"><pre>bin/
    hello                 <span class="pl-c"><span class="pl-c">#</span> command executable</span>
pkg/
    linux_amd64/          <span class="pl-c"><span class="pl-c">#</span> this will reflect your OS and architecture</span>
        github.com/user/
            stringutil.a  <span class="pl-c"><span class="pl-c">#</span> package object</span>
src/
    github.com/user/
        hello/
            hello.go      <span class="pl-c"><span class="pl-c">#</span> command source</span>
        stringutil/
            reverse.go    <span class="pl-c"><span class="pl-c">#</span> package source</span></pre></div>
<p>请注意，<code>go install</code>将<code>stringutil.a</code>对象放置在<code>pkg/linux_amd64</code>镜像源目录中的目录中。这样未来的<code>go</code>工具调用可以找到包对象并避免不必要地重新编译包。该<code>linux_amd64</code>部分有助于交叉编译，并将反映您的系统的操作系统和体系结构。</p>
<p><strong>Go命令可执行文件是静态链接的</strong>，包对象不需要存在来运行Go程序。</p>
<blockquote>
<p>包名称</p>
</blockquote>
<p>Go源文件中的第一条语句必须是</p>
<div class="highlight highlight-source-shell"><pre>package name</pre></div>
<p>这里<code>name</code>是对进口的包的默认名称。（包中的所有文件都必须使用相同的文件<code>name</code>）</p>
<p>Go的惯例是包名称是导入路径的最后一个元素：<code>crypto/rot13</code>应该命名导入为“ ” 的包rot13。</p>
<p>可执行命令必须始终使用<code>package main</code>。</p>
<p>没有要求软件包名称在链接到一个二进制文件的所有软件包中唯一，<strong>只需要导入路径（它们的完整文件名）是唯一的</strong>。</p>
<p>请参阅<a href="http://127.0.0.1:8080/doc/effective_go.html#names" rel="nofollow">Effective Go</a>详细了解Go的命名约定。</p>
<blockquote>
<p>测试</p>
</blockquote>
<p>Go有一个由<code>go test</code>命令和<code>testing</code>包组成的轻量级测试框架。</p>
<p>您通过创建一个名称以文件名结尾的文件来编写一个测试<code>_test.go</code> ，其中包含以TestXXX签名 命名的函数<code>func (t *testing.T)</code>。测试框架运行每个这样的功能; 如果函数调用失败函数（如t.Error或）<code>t.Fail</code>，则认为测试失败。</p>
<p><code>stringutil</code>通过创建<code>$GOPATH/src/github.com/user/stringutil/reverse_test.go</code>包含以下Go代码的文件 向测试包 添加测试。</p>
<div class="highlight highlight-source-go"><pre><span class="pl-k">package</span> stringutil

<span class="pl-k">import</span> <span class="pl-s"><span class="pl-pds">"</span>testing<span class="pl-pds">"</span></span>

<span class="pl-k">func</span> <span class="pl-en">TestReverse</span>(<span class="pl-v">t</span> *<span class="pl-v">testing</span>.<span class="pl-v">T</span>) {
	<span class="pl-smi">cases</span> <span class="pl-k">:=</span> []<span class="pl-k">struct</span> {
		in, want <span class="pl-k">string</span>
	}{
		{<span class="pl-s"><span class="pl-pds">"</span>Hello, world<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>dlrow ,olleH<span class="pl-pds">"</span></span>},
		{<span class="pl-s"><span class="pl-pds">"</span>Hello, 世界<span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span>界世 ,olleH<span class="pl-pds">"</span></span>},
		{<span class="pl-s"><span class="pl-pds">"</span><span class="pl-pds">"</span></span>, <span class="pl-s"><span class="pl-pds">"</span><span class="pl-pds">"</span></span>},
	}
	<span class="pl-k">for</span> <span class="pl-smi">_</span>, <span class="pl-smi">c</span> <span class="pl-k">:=</span> <span class="pl-k">range</span> cases {
		<span class="pl-smi">got</span> <span class="pl-k">:=</span> <span class="pl-c1">Reverse</span>(c.<span class="pl-smi">in</span>)
		<span class="pl-k">if</span> got != c.<span class="pl-smi">want</span> {
			t.<span class="pl-c1">Errorf</span>(<span class="pl-s"><span class="pl-pds">"</span>Reverse(<span class="pl-c1">%q</span>) == <span class="pl-c1">%q</span>, want <span class="pl-c1">%q</span><span class="pl-pds">"</span></span>, c.<span class="pl-smi">in</span>, got, c.<span class="pl-smi">want</span>)
		}
	}
}</pre></div>
<p>然后运行测试<code>go test</code>：</p>
<div class="highlight highlight-source-shell"><pre>$ go <span class="pl-c1">test</span> github.com/user/stringutil
ok  	github.com/user/stringutil 0.165s</pre></div>
<p>与往常一样，如果您正在go从软件包目录运行该工具，则可以省略软件包路径：</p>
<div class="highlight highlight-source-shell"><pre>$ go <span class="pl-c1">test</span>
ok  	github.com/user/stringutil 0.165s</pre></div>
<p>运行<code>go help test</code>并查看 测试包文档以获取更多详细信息。</p>
<blockquote>
<p>远程软件包</p>
</blockquote>
<p>导入路径可以描述如何使用Git或Mercurial等版本控制系统获取软件包源代码。该go工具使用此属性从远程存储库自动获取软件包。例如，本文档中描述的示例也保存在GitHub托管的Git存储库中<code>github.com/golang/example</code>。如果您在存储库的导入路径中包含存储库URL，<code>go get</code>将自动获取，构建和安装它：</p>
<div class="highlight highlight-source-shell"><pre>$ go get github.com/golang/example/hello
$ <span class="pl-smi">$GOPATH</span>/bin/hello
Hello, Go examples<span class="pl-k">!</span></pre></div>
<p>如果指定的软件包不在工作区中，<code>go get</code>则将其放入由指定的第一个工作区内<code>GOPATH</code>。（如果包已经存在，则<code>go get</code>跳过远程抓取并且行为与<code>go install</code>相同）</p>
<p>发出上述<code>go get</code>命令后，工作空间目录树现在应该如下所示：</p>
<div class="highlight highlight-source-go"><pre>bin/
    hello                           # command executable
pkg/
    linux_amd64/
        github.<span class="pl-smi">com</span>/golang/example/
            stringutil.<span class="pl-smi">a</span>            # <span class="pl-k">package</span> object
        github.<span class="pl-smi">com</span>/user/
            stringutil.<span class="pl-smi">a</span>            # <span class="pl-k">package</span> object
src/
    github.<span class="pl-smi">com</span>/golang/example/
	.<span class="pl-smi">git</span>/                       # <span class="pl-v">Git</span> repository metadata
        hello/
            hello.<span class="pl-smi">go</span>                # command source
        stringutil/
            reverse.<span class="pl-smi">go</span>              # <span class="pl-k">package</span> source
            reverse_test.<span class="pl-smi">go</span>         # test source
    github.<span class="pl-smi">com</span>/user/
        hello/
            hello.<span class="pl-smi">go</span>                # command source
        stringutil/
            reverse.<span class="pl-smi">go</span>              # <span class="pl-k">package</span> source
            reverse_test.<span class="pl-smi">go</span>         # test source</pre></div>
<p>hello在GitHub上托管的命令取决于<code>stringutil</code>同一个存储库中的软件包。在导入<code>hello.go</code>文件中使用相同的导入路径约定，所以<code>go get</code>命令能够找到并安装相关的包了。</p>
<p>导入<code>“github.com/golang/example/stringutil”</code>这个约定是让你的Go软件包可供其他人使用的最简单的方法。在转到维基 和<code>godoc.org</code> 提供外部围棋项目清单。</p>
<p>有关在go工具中使用远程存储库的更多信息，请参阅 <a href="http://127.0.0.1:8080/cmd/go/#hdr-Remote_import_paths" rel="nofollow">go help importpath</a>。</p>
</article>
  </div>

  </div>

  <details class="details-reset details-overlay details-overlay-dark">
    <summary data-hotkey="l" aria-label="Jump to line"></summary>
    <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast linejump" aria-label="Jump to line">
      <!-- '"` --><!-- </textarea></xmp> --></option></form><form class="js-jump-to-line-form Box-body d-flex" action="" accept-charset="UTF-8" method="get"><input name="utf8" type="hidden" value="&#x2713;" />
        <input class="form-control flex-auto mr-3 linejump-input js-jump-to-line-field" type="text" placeholder="Jump to line&hellip;" aria-label="Jump to line" autofocus>
        <button type="submit" class="btn" data-close-dialog>Go</button>
</form>    </details-dialog>
  </details>


  </div>
  <div class="modal-backdrop js-touch-events"></div>
</div>

    </div>
  </div>

  </div>

        
<div class="footer container-lg px-3" role="contentinfo">
  <div class="position-relative d-flex flex-justify-between pt-6 pb-2 mt-6 f6 text-gray border-top border-gray-light ">
    <ul class="list-style-none d-flex flex-wrap ">
      <li class="mr-3">&copy; 2018 <span title="0.14065s from unicorn-75bc777dc4-76p24">GitHub</span>, Inc.</li>
        <li class="mr-3"><a data-ga-click="Footer, go to terms, text:terms" href="https://github.com/site/terms">Terms</a></li>
        <li class="mr-3"><a data-ga-click="Footer, go to privacy, text:privacy" href="https://github.com/site/privacy">Privacy</a></li>
        <li class="mr-3"><a href="https://help.github.com/articles/github-security/" data-ga-click="Footer, go to security, text:security">Security</a></li>
        <li class="mr-3"><a href="https://status.github.com/" data-ga-click="Footer, go to status, text:status">Status</a></li>
        <li><a data-ga-click="Footer, go to help, text:help" href="https://help.github.com">Help</a></li>
    </ul>

    <a aria-label="Homepage" title="GitHub" class="footer-octicon mr-lg-4" href="https://github.com">
      <svg height="24" class="octicon octicon-mark-github" viewBox="0 0 16 16" version="1.1" width="24" aria-hidden="true"><path fill-rule="evenodd" d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.013 8.013 0 0 0 16 8c0-4.42-3.58-8-8-8z"/></svg>
</a>
   <ul class="list-style-none d-flex flex-wrap ">
        <li class="mr-3"><a data-ga-click="Footer, go to contact, text:contact" href="https://github.com/contact">Contact GitHub</a></li>
        <li class="mr-3"><a href="https://github.com/pricing" data-ga-click="Footer, go to Pricing, text:Pricing">Pricing</a></li>
      <li class="mr-3"><a href="https://developer.github.com" data-ga-click="Footer, go to api, text:api">API</a></li>
      <li class="mr-3"><a href="https://training.github.com" data-ga-click="Footer, go to training, text:training">Training</a></li>
        <li class="mr-3"><a href="https://blog.github.com" data-ga-click="Footer, go to blog, text:blog">Blog</a></li>
        <li><a data-ga-click="Footer, go to about, text:about" href="https://github.com/about">About</a></li>

    </ul>
  </div>
  <div class="d-flex flex-justify-center pb-6">
    <span class="f6 text-gray-light"></span>
  </div>
</div>



  <div id="ajax-error-message" class="ajax-error-message flash flash-error">
    <svg class="octicon octicon-alert" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M8.893 1.5c-.183-.31-.52-.5-.887-.5s-.703.19-.886.5L.138 13.499a.98.98 0 0 0 0 1.001c.193.31.53.501.886.501h13.964c.367 0 .704-.19.877-.5a1.03 1.03 0 0 0 .01-1.002L8.893 1.5zm.133 11.497H6.987v-2.003h2.039v2.003zm0-3.004H6.987V5.987h2.039v4.006z"/></svg>
    <button type="button" class="flash-close js-ajax-error-dismiss" aria-label="Dismiss error">
      <svg class="octicon octicon-x" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.48 8l3.75 3.75-1.48 1.48L6 9.48l-3.75 3.75-1.48-1.48L4.52 8 .77 4.25l1.48-1.48L6 6.52l3.75-3.75 1.48 1.48L7.48 8z"/></svg>
    </button>
    You can’t perform that action at this time.
  </div>


    <script crossorigin="anonymous" integrity="sha512-RJ1ufbxsSbKjRCyYvinsPNKvTBvcvvKUvEOJ8g+GjtWI5SuRr+QPBlZcvRDws4H9YwAgdQFcGxfL8UbwEfdI7A==" type="application/javascript" src="https://assets-cdn.github.com/assets/compat-daf14de28fadf1e2bc40d100cb773e2b.js"></script>
    <script crossorigin="anonymous" integrity="sha512-vuSiumVQ19SCEH15AK/fmR75d/qAL38iC7QVE4YnlvgNa7uBa92nr/qPt9zS3E6CrWpq7wa9awDPuzphrnHT5w==" type="application/javascript" src="https://assets-cdn.github.com/assets/frameworks-bf2c22b1c392529e298b629d4e812b82.js"></script>
    
    <script crossorigin="anonymous" async="async" integrity="sha512-RKQzJE/1Sb6lFY1veyzarSkJobDSP1D9G1OWe1AQJ072Oz0IqOPpWwxJj++zf0PkMknWsXXY26Q76AY/2euAdg==" type="application/javascript" src="https://assets-cdn.github.com/assets/github-e4b651bc3a0d2b00fbf2dce9b73252a8.js"></script>
    
    
    
  <div class="js-stale-session-flash stale-session-flash flash flash-warn flash-banner d-none">
    <svg class="octicon octicon-alert" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M8.893 1.5c-.183-.31-.52-.5-.887-.5s-.703.19-.886.5L.138 13.499a.98.98 0 0 0 0 1.001c.193.31.53.501.886.501h13.964c.367 0 .704-.19.877-.5a1.03 1.03 0 0 0 .01-1.002L8.893 1.5zm.133 11.497H6.987v-2.003h2.039v2.003zm0-3.004H6.987V5.987h2.039v4.006z"/></svg>
    <span class="signed-in-tab-flash">You signed in with another tab or window. <a href="">Reload</a> to refresh your session.</span>
    <span class="signed-out-tab-flash">You signed out in another tab or window. <a href="">Reload</a> to refresh your session.</span>
  </div>
  <div class="facebox" id="facebox" style="display:none;">
  <div class="facebox-popup">
    <div class="facebox-content" role="dialog" aria-labelledby="facebox-header" aria-describedby="facebox-description">
    </div>
    <button type="button" class="facebox-close js-facebox-close" aria-label="Close modal">
      <svg class="octicon octicon-x" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.48 8l3.75 3.75-1.48 1.48L6 9.48l-3.75 3.75-1.48-1.48L4.52 8 .77 4.25l1.48-1.48L6 6.52l3.75-3.75 1.48 1.48L7.48 8z"/></svg>
    </button>
  </div>
</div>

  <template id="site-details-dialog">
  <details class="details-reset details-overlay details-overlay-dark lh-default text-gray-dark" open>
    <summary aria-haspopup="dialog" aria-label="Close dialog"></summary>
    <details-dialog class="Box Box--overlay d-flex flex-column anim-fade-in fast">
      <button class="m-3 btn-octicon position-absolute right-0 top-0" type="button" aria-label="Close dialog" data-close-dialog>
        <svg class="octicon octicon-x" viewBox="0 0 12 16" version="1.1" width="12" height="16" aria-hidden="true"><path fill-rule="evenodd" d="M7.48 8l3.75 3.75-1.48 1.48L6 9.48l-3.75 3.75-1.48-1.48L4.52 8 .77 4.25l1.48-1.48L6 6.52l3.75-3.75 1.48 1.48L7.48 8z"/></svg>
      </button>
      <div class="octocat-spinner my-6 js-details-dialog-spinner"></div>
    </details-dialog>
  </details>
</template>

  <div class="Popover js-hovercard-content position-absolute" style="display: none; outline: none;" tabindex="0">
  <div class="Popover-message Popover-message--bottom-left Popover-message--large Box box-shadow-large" style="width:360px;">
  </div>
</div>

<div id="hovercard-aria-description" class="sr-only">
  Press h to open a hovercard with more details.
</div>


  </body>
</html>

