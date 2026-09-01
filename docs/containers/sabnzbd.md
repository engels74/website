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
<tr><td><div id="tag25113" onclick="CopyToClipboard('tag25113');return false;" class="tag-decoration">nightly</div><div id="tag27761" onclick="CopyToClipboard('tag27761');return false;" class="tag-decoration">nightly-787b94a</div><div id="tag6655" onclick="CopyToClipboard('tag6655');return false;" class="tag-decoration">nightly-20915cc626ceb5071ad5a1eba9d49f2b0a5f261c</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/787b94a5df070d32386d4030ce8b0d20628d616f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33512354000" target="_blank">2026-09-01 13:15:59</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag13156" onclick="CopyToClipboard('tag13156');return false;" class="tag-decoration">release</div><div id="tag9492" onclick="CopyToClipboard('tag9492');return false;" class="tag-decoration">release-3699da3</div><div id="tag15535" onclick="CopyToClipboard('tag15535');return false;" class="tag-decoration">release-5.1.2</div><div id="tag6622" onclick="CopyToClipboard('tag6622');return false;" class="tag-decoration">release-v5</div><div id="tag13955" onclick="CopyToClipboard('tag13955');return false;" class="tag-decoration">release-v5.1</div><div id="tag29194" onclick="CopyToClipboard('tag29194');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3699da399bd995c96fef64e914b2ef5e02caa282" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919084624" target="_blank">2026-08-26 01:28:09</a></td></tr>
<tr><td><div id="tag23096" onclick="CopyToClipboard('tag23096');return false;" class="tag-decoration">testing</div><div id="tag2493" onclick="CopyToClipboard('tag2493');return false;" class="tag-decoration">testing-00935f0</div><div id="tag7684" onclick="CopyToClipboard('tag7684');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag4084" onclick="CopyToClipboard('tag4084');return false;" class="tag-decoration">testing-v5</div><div id="tag32079" onclick="CopyToClipboard('tag32079');return false;" class="tag-decoration">testing-v5.1</div><div id="tag11056" onclick="CopyToClipboard('tag11056');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/00935f0d6744379ad94969d7f14fa72e46fe68c7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919082616" target="_blank">2026-08-26 01:28:07</a></td></tr>
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
