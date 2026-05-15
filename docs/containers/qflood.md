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
<tr><td><div id="tag19172" onclick="CopyToClipboard('tag19172');return false;" class="tag-decoration">nightly</div><div id="tag5085" onclick="CopyToClipboard('tag5085');return false;" class="tag-decoration">nightly-42ba6a9</div><div id="tag2790" onclick="CopyToClipboard('tag2790');return false;" class="tag-decoration">nightly-5.2.0--25919415228</div><div id="tag7998" onclick="CopyToClipboard('tag7998');return false;" class="tag-decoration">nightly-v5</div><div id="tag32432" onclick="CopyToClipboard('tag32432');return false;" class="tag-decoration">nightly-v5.2</div><div id="tag23487" onclick="CopyToClipboard('tag23487');return false;" class="tag-decoration">nightly-v5.2.0</div></td><td>nightly</td><td><a href="https://github.com/engels74/qflood/commit/42ba6a9ac3565f6c5a7efcf748a3a73c75ac4e79" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/25925785790" target="_blank">2026-05-15 15:19:28</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag32516" onclick="CopyToClipboard('tag32516');return false;" class="tag-decoration">release</div><div id="tag8092" onclick="CopyToClipboard('tag8092');return false;" class="tag-decoration">release-e07d1b0</div><div id="tag27459" onclick="CopyToClipboard('tag27459');return false;" class="tag-decoration">release-5.2.0--4.14.1</div><div id="tag22070" onclick="CopyToClipboard('tag22070');return false;" class="tag-decoration">release-v5</div><div id="tag22642" onclick="CopyToClipboard('tag22642');return false;" class="tag-decoration">release-v5.2</div><div id="tag13288" onclick="CopyToClipboard('tag13288');return false;" class="tag-decoration">release-v5.2.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/qflood/commit/e07d1b0ceff9594a8f03d26165e63961a9aae025" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/25932385705" target="_blank">2026-05-15 17:40:50</a></td></tr>
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
