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
<tr><td><div id="tag1259" onclick="CopyToClipboard('tag1259');return false;" class="tag-decoration">legacy</div><div id="tag20040" onclick="CopyToClipboard('tag20040');return false;" class="tag-decoration">legacy-4.3.9</div><div id="tag14644" onclick="CopyToClipboard('tag14644');return false;" class="tag-decoration">legacy-177c180</div><div id="tag7119" onclick="CopyToClipboard('tag7119');return false;" class="tag-decoration">legacy-v4</div><div id="tag17315" onclick="CopyToClipboard('tag17315');return false;" class="tag-decoration">legacy-v4.3</div><div id="tag6236" onclick="CopyToClipboard('tag6236');return false;" class="tag-decoration">legacy-v4.3.9</div></td><td>Fixed to v4.3.9</td><td><a href="https://github.com/engels74/qbittorrent/commit/177c180dddf463793ebf94730428f3ddcc159c0b" target="_blank">Upstream update: alpinevpn-4dcfd96 => alpinevpn-213d573</a></td><td><a href="https://github.com/engels74/qbittorrent/actions/runs/20911151619" target="_blank">2026-01-12 07:21:37</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag5250" onclick="CopyToClipboard('tag5250');return false;" class="tag-decoration">release</div><div id="tag27924" onclick="CopyToClipboard('tag27924');return false;" class="tag-decoration">release-3742c34</div><div id="tag18884" onclick="CopyToClipboard('tag18884');return false;" class="tag-decoration">release-5.1.4</div><div id="tag15155" onclick="CopyToClipboard('tag15155');return false;" class="tag-decoration">release-v5</div><div id="tag16099" onclick="CopyToClipboard('tag16099');return false;" class="tag-decoration">release-v5.1</div><div id="tag20938" onclick="CopyToClipboard('tag20938');return false;" class="tag-decoration">release-v5.1.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/qbittorrent/commit/3742c34b3f563636e1e7dd5e6f9a988c9114022b" target="_blank">Upstream update: alpinevpn-213d573 => alpinevpn-89f692c</a></td><td><a href="https://github.com/engels74/qbittorrent/actions/runs/20935301549" target="_blank">2026-01-12 21:17:22</a></td></tr>
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
