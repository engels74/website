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
<tr><td><div id="tag8850" onclick="CopyToClipboard('tag8850');return false;" class="tag-decoration">nightly</div><div id="tag26746" onclick="CopyToClipboard('tag26746');return false;" class="tag-decoration">nightly-5c9cf0a</div><div id="tag728" onclick="CopyToClipboard('tag728');return false;" class="tag-decoration">nightly-2668f1cd267ce13722c9f695337a8f7d134f3fba</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/5c9cf0a3dd11d2cc87f60fc4020b2fd368a8a44a" target="_blank">Upstream update: alpinevpn-4699fa7 => alpinevpn-f4e73db</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25605042754" target="_blank">2026-05-09 15:43:09</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag31497" onclick="CopyToClipboard('tag31497');return false;" class="tag-decoration">release</div><div id="tag29183" onclick="CopyToClipboard('tag29183');return false;" class="tag-decoration">release-f6d19f7</div><div id="tag10321" onclick="CopyToClipboard('tag10321');return false;" class="tag-decoration">release-5.0.1</div><div id="tag4889" onclick="CopyToClipboard('tag4889');return false;" class="tag-decoration">release-v5</div><div id="tag27454" onclick="CopyToClipboard('tag27454');return false;" class="tag-decoration">release-v5.0</div><div id="tag25568" onclick="CopyToClipboard('tag25568');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f6d19f79496d9dbce75a040beca45c30ecbc9fb5" target="_blank">Upstream update: alpinevpn-4699fa7 => alpinevpn-f4e73db</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25605042893" target="_blank">2026-05-09 15:43:10</a></td></tr>
<tr><td><div id="tag24666" onclick="CopyToClipboard('tag24666');return false;" class="tag-decoration">testing</div><div id="tag7177" onclick="CopyToClipboard('tag7177');return false;" class="tag-decoration">testing-2b55556</div><div id="tag27961" onclick="CopyToClipboard('tag27961');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag848" onclick="CopyToClipboard('tag848');return false;" class="tag-decoration">testing-v5</div><div id="tag6706" onclick="CopyToClipboard('tag6706');return false;" class="tag-decoration">testing-v5.0</div><div id="tag7961" onclick="CopyToClipboard('tag7961');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b5555662f7d34c27829058643eff45c1b6eee87" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254956" target="_blank">2026-05-01 21:37:10</a></td></tr>
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
