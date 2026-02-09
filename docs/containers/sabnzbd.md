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
<tr><td><div id="tag11987" onclick="CopyToClipboard('tag11987');return false;" class="tag-decoration">nightly</div><div id="tag10473" onclick="CopyToClipboard('tag10473');return false;" class="tag-decoration">nightly-86be022</div><div id="tag16763" onclick="CopyToClipboard('tag16763');return false;" class="tag-decoration">nightly-7f8d7d80d272563c9c1d5a7bb2547922b403ebe4</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/86be0227d197c1e24d351c93c54a53ca492aa84b" target="_blank">Version update: 40ea82a8bb28402c8d924c76b0b931f7e1a6227e => 7f8d7d80d272563c9c1d5a7bb2547922b403ebe4</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21839538618" target="_blank">2026-02-09 20:32:10</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26639" onclick="CopyToClipboard('tag26639');return false;" class="tag-decoration">release</div><div id="tag5352" onclick="CopyToClipboard('tag5352');return false;" class="tag-decoration">release-252442e</div><div id="tag18079" onclick="CopyToClipboard('tag18079');return false;" class="tag-decoration">release-4.5.5</div><div id="tag19382" onclick="CopyToClipboard('tag19382');return false;" class="tag-decoration">release-v4</div><div id="tag25342" onclick="CopyToClipboard('tag25342');return false;" class="tag-decoration">release-v4.5</div><div id="tag24091" onclick="CopyToClipboard('tag24091');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/252442ee081e7bffb07db68d74238fe65fe61492" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823272944" target="_blank">2026-02-09 11:29:10</a></td></tr>
<tr><td><div id="tag27356" onclick="CopyToClipboard('tag27356');return false;" class="tag-decoration">testing</div><div id="tag32387" onclick="CopyToClipboard('tag32387');return false;" class="tag-decoration">testing-3dc0cdf</div><div id="tag10846" onclick="CopyToClipboard('tag10846');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag12868" onclick="CopyToClipboard('tag12868');return false;" class="tag-decoration">testing-v4</div><div id="tag2358" onclick="CopyToClipboard('tag2358');return false;" class="tag-decoration">testing-v4.5</div><div id="tag27719" onclick="CopyToClipboard('tag27719');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3dc0cdf9be0128f86ab1d3137f11ee412fbc5fa6" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823273556" target="_blank">2026-02-09 11:29:12</a></td></tr>
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
