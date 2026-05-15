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
<tr><td><div id="tag7" onclick="CopyToClipboard('tag7');return false;" class="tag-decoration">nightly</div><div id="tag10890" onclick="CopyToClipboard('tag10890');return false;" class="tag-decoration">nightly-36b38ca</div><div id="tag4796" onclick="CopyToClipboard('tag4796');return false;" class="tag-decoration">nightly-8069361faaf6f00d384af990634538c28bcec619</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/36b38ca3357ed5ef0f961301b727dd4a9d85193f" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25941445796" target="_blank">2026-05-15 21:07:14</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag27808" onclick="CopyToClipboard('tag27808');return false;" class="tag-decoration">release</div><div id="tag8187" onclick="CopyToClipboard('tag8187');return false;" class="tag-decoration">release-4bec790</div><div id="tag3448" onclick="CopyToClipboard('tag3448');return false;" class="tag-decoration">release-5.0.3</div><div id="tag25184" onclick="CopyToClipboard('tag25184');return false;" class="tag-decoration">release-v5</div><div id="tag11741" onclick="CopyToClipboard('tag11741');return false;" class="tag-decoration">release-v5.0</div><div id="tag9473" onclick="CopyToClipboard('tag9473');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4bec790507a8b73efeb2c4217246e129a9c357a4" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932485279" target="_blank">2026-05-15 17:42:59</a></td></tr>
<tr><td><div id="tag13409" onclick="CopyToClipboard('tag13409');return false;" class="tag-decoration">testing</div><div id="tag2484" onclick="CopyToClipboard('tag2484');return false;" class="tag-decoration">testing-89eb06e</div><div id="tag23230" onclick="CopyToClipboard('tag23230');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag4093" onclick="CopyToClipboard('tag4093');return false;" class="tag-decoration">testing-v5</div><div id="tag10631" onclick="CopyToClipboard('tag10631');return false;" class="tag-decoration">testing-v5.0</div><div id="tag6613" onclick="CopyToClipboard('tag6613');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/89eb06ea7ddb5c4fd27028fdbf0b1df485f7f8a8" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932492370" target="_blank">2026-05-15 17:43:09</a></td></tr>
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
