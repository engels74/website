---
hide:
  - toc
title: engels74/sabnzbd
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/sabnzbd){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/sabnzbd){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://sabnzbd.org){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/sabnzbd.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [SABnzbd](https://hotio.dev/containers/sabnzbd) Docker image, that includes ffprobe, at `/app/bin/ffprobe`. Useful for scripts.

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
<tr><td><div id="tag25758" onclick="CopyToClipboard('tag25758');return false;" class="tag-decoration">nightly</div><div id="tag5783" onclick="CopyToClipboard('tag5783');return false;" class="tag-decoration">nightly-362d8c2</div><div id="tag5532" onclick="CopyToClipboard('tag5532');return false;" class="tag-decoration">nightly-e1cd1eed83c6f877ef27586f5cebf13448c07794</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/362d8c28884138092f24eb335848b07c8d62371a" target="_blank">Version update: a4de70496713ea705ee275b3c75df1b499b90dbb => e1cd1eed83c6f877ef27586f5cebf13448c07794</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21411423407" target="_blank">2026-01-27 19:38:04</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag6277" onclick="CopyToClipboard('tag6277');return false;" class="tag-decoration">release</div><div id="tag28994" onclick="CopyToClipboard('tag28994');return false;" class="tag-decoration">release-fe2b475</div><div id="tag16861" onclick="CopyToClipboard('tag16861');return false;" class="tag-decoration">release-4.5.5</div><div id="tag29443" onclick="CopyToClipboard('tag29443');return false;" class="tag-decoration">release-v4</div><div id="tag28107" onclick="CopyToClipboard('tag28107');return false;" class="tag-decoration">release-v4.5</div><div id="tag29648" onclick="CopyToClipboard('tag29648');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/fe2b475ca1dfab2e96ed4e5a1d8eaa7dfe822c8b" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21389829582" target="_blank">2026-01-27 08:23:32</a></td></tr>
<tr><td><div id="tag23342" onclick="CopyToClipboard('tag23342');return false;" class="tag-decoration">testing</div><div id="tag30879" onclick="CopyToClipboard('tag30879');return false;" class="tag-decoration">testing-0570f77</div><div id="tag19483" onclick="CopyToClipboard('tag19483');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag6568" onclick="CopyToClipboard('tag6568');return false;" class="tag-decoration">testing-v4</div><div id="tag28880" onclick="CopyToClipboard('tag28880');return false;" class="tag-decoration">testing-v4.5</div><div id="tag18184" onclick="CopyToClipboard('tag18184');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/0570f77391285ec4a93a027d57253635e4b45084" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21389830108" target="_blank">2026-01-27 08:23:33</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name sabnzbd \
        -p 8080:8080 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e WEBUI_PORTS="8080/tcp,8080/udp" \
        -e ARGS="" \
        -e TZ="Etc/UTC" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/sabnzbd
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      sabnzbd:
        container_name: sabnzbd
        image: ghcr.io/engels74/sabnzbd
        ports:
          - "8080:8080"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=8080/tcp,8080/udp
          - ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

--8<-- "includes/wireguard.md"
