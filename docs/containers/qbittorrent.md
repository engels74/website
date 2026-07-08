---
hide:
  - toc
title: engels74/qbittorrent
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/qbittorrent){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/qbittorrent){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/qbittorrent/qbittorrent){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/qbittorrent.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [qBittorrent](https://hotio.dev/containers/qbittorrent) Docker image, that uses [libtorrent v2.x](https://github.com/userdocs/qbittorrent-nox-static/releases) by default.

    Hotio [recently](https://github.com/hotio/qbittorrent/commit/e8dada05befebf51d73669a05b09ef046c6f69e6) added the option to define by ENV if you want to use libtorrent v1 or v2. This one uses `v2` by default.

    This also still includes VueTorrent in the image, as hotio also removed support for themes.

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
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag25789" onclick="CopyToClipboard('tag25789');return false;" class="tag-decoration">release</div><div id="tag1947" onclick="CopyToClipboard('tag1947');return false;" class="tag-decoration">release-a745de4</div><div id="tag825" onclick="CopyToClipboard('tag825');return false;" class="tag-decoration">release-5.2.3</div><div id="tag9895" onclick="CopyToClipboard('tag9895');return false;" class="tag-decoration">release-v5</div><div id="tag6479" onclick="CopyToClipboard('tag6479');return false;" class="tag-decoration">release-v5.2</div><div id="tag9401" onclick="CopyToClipboard('tag9401');return false;" class="tag-decoration">release-v5.2.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/qbittorrent/commit/a745de430d6fd1ca604f7e1647c8cec0e679f7ce" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/qbittorrent/actions/runs/28907497238" target="_blank">2026-07-08 00:06:02</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name qbittorrent \
        -p 8080:8080 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e WEBUI_PORTS="8080/tcp,8080/udp" \
        -e LIBTORRENT="v2" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/qbittorrent
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      qbittorrent:
        container_name: qbittorrent
        image: ghcr.io/engels74/qbittorrent
        ports:
          - "8080:8080"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=8080/tcp,8080/udp
          - LIBTORRENT=v2
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

## Alternative Web UI

This image comes bundled with the alternative Web UI [VueTorrent](https://github.com/VueTorrent/VueTorrent) (`/app/vuetorrent`). Nightwalker is removed, as it is no longer maintained.

--8<-- "includes/wireguard.md"
