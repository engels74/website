---
hide:
  - toc
title: engels74/qflood
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/qflood){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/qflood){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/jesec/flood){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/qflood.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [rflood](https://hotio.dev/containers/rflood) Docker image, that uses qBittorrent instead of rtorrent. The qflood image has both "releases" and "nightly support". The included [qBittorrent](https://github.com/userdocs/qbittorrent-nox-static) uses libtorrent v2.x.

???+ info "What is nightly?"

    Nightly means it updates automatically after a successful run of [this workflow file](https://github.com/jesec/flood/actions/workflows/publish-rolling.yml). This means that whenever the official flood repository receives a push commit, this docker image should automatically be updated. All thanks to hotio's brilliant setup.

<div id="tags-table">
  <table>
    <thead>
      <tr>
        <th>Tags <span class="twemoji" title="Click Tag to Copy"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M11 9h2V7h-2m1 13c-4.41 0-8-3.59-8-8s3.59-8 8-8 8 3.59 8 8-3.59 8-8 8m0-18A10 10 0 0 0 2 12a10 10 0 0 0 10 10 10 10 0 0 0 10-10A10 10 0 0 0 12 2m-1 15h2v-6h-2z"></path></svg></span></th>
        <th>Description</th>
        <th>Commit</th>
        <th>Last Updated</th>
      </tr>
    </thead>
    <tbody id="tags-table-body">
<tr><td><div id="tag21648" onclick="CopyToClipboard('tag21648');return false;" class="tag-decoration">nightly</div><div id="tag1663" onclick="CopyToClipboard('tag1663');return false;" class="tag-decoration">nightly-83af183</div><div id="tag30537" onclick="CopyToClipboard('tag30537');return false;" class="tag-decoration">nightly-5.1.4--24597261167</div><div id="tag22020" onclick="CopyToClipboard('tag22020');return false;" class="tag-decoration">nightly-v5</div><div id="tag9005" onclick="CopyToClipboard('tag9005');return false;" class="tag-decoration">nightly-v5.1</div><div id="tag28052" onclick="CopyToClipboard('tag28052');return false;" class="tag-decoration">nightly-v5.1.4</div></td><td>nightly</td><td><a href="https://github.com/engels74/qflood/commit/83af18348ad83d4231182da2e3295b44e098bcdc" target="_blank">Version update: 5.1.4--24597261167 => 5.1.4--24597261167</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/24791114908" target="_blank">2026-04-22 16:51:51</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag1252" onclick="CopyToClipboard('tag1252');return false;" class="tag-decoration">release</div><div id="tag1915" onclick="CopyToClipboard('tag1915');return false;" class="tag-decoration">release-29ddf2a</div><div id="tag20320" onclick="CopyToClipboard('tag20320');return false;" class="tag-decoration">release-5.1.4--4.13.10</div><div id="tag16807" onclick="CopyToClipboard('tag16807');return false;" class="tag-decoration">release-v5</div><div id="tag26496" onclick="CopyToClipboard('tag26496');return false;" class="tag-decoration">release-v5.1</div><div id="tag1948" onclick="CopyToClipboard('tag1948');return false;" class="tag-decoration">release-v5.1.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/qflood/commit/29ddf2aa9d6cf09a38e2c80a1f7acc5b7adbd7cf" target="_blank">Version update: 5.1.4--4.13.9 => 5.1.4--4.13.10</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/25211741245" target="_blank">2026-05-01 10:50:34</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name qflood \
        -p 8080:8080 \
        -p 3000:3000 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e LIBTORRENT="v2" \
        -e FLOOD_AUTH="true" \
        -e ARGS="" \
        -e FLOOD_ARGS="" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/qflood
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      qflood:
        container_name: qflood
        image: ghcr.io/engels74/qflood
        ports:
          - "8080:8080"
          - "3000:3000"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - LIBTORRENT=v2
          - FLOOD_AUTH=true
          - ARGS
          - FLOOD_ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

## Changing the WebUI port

Under certain circumstances it's required to run the WebUI on a different internal port, you can do that by modifying the environment variable `WEBUI_PORTS` accordingly. It should be in the format `xxxx/tcp,xxxx/udp`, take a look at the default with `docker logs` (variable is printed at container start) or `docker inspect`.

--8<-- "includes/wireguard.md"
