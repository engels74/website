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
<tr><td><div id="tag14388" onclick="CopyToClipboard('tag14388');return false;" class="tag-decoration">nightly</div><div id="tag28327" onclick="CopyToClipboard('tag28327');return false;" class="tag-decoration">nightly-36b38ca</div><div id="tag6839" onclick="CopyToClipboard('tag6839');return false;" class="tag-decoration">nightly-8069361faaf6f00d384af990634538c28bcec619</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/36b38ca3357ed5ef0f961301b727dd4a9d85193f" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25941445796" target="_blank">2026-05-15 21:07:14</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag11950" onclick="CopyToClipboard('tag11950');return false;" class="tag-decoration">release</div><div id="tag1867" onclick="CopyToClipboard('tag1867');return false;" class="tag-decoration">release-fe37017</div><div id="tag17370" onclick="CopyToClipboard('tag17370');return false;" class="tag-decoration">release-5.0.3</div><div id="tag25414" onclick="CopyToClipboard('tag25414');return false;" class="tag-decoration">release-v5</div><div id="tag26062" onclick="CopyToClipboard('tag26062');return false;" class="tag-decoration">release-v5.0</div><div id="tag19830" onclick="CopyToClipboard('tag19830');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/fe3701758606402e06f29f24e8186bc9408eabe7" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25941446017" target="_blank">2026-05-15 21:07:14</a></td></tr>
<tr><td><div id="tag22543" onclick="CopyToClipboard('tag22543');return false;" class="tag-decoration">testing</div><div id="tag15577" onclick="CopyToClipboard('tag15577');return false;" class="tag-decoration">testing-2002546</div><div id="tag31984" onclick="CopyToClipboard('tag31984');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag22753" onclick="CopyToClipboard('tag22753');return false;" class="tag-decoration">testing-v5</div><div id="tag9914" onclick="CopyToClipboard('tag9914');return false;" class="tag-decoration">testing-v5.0</div><div id="tag31357" onclick="CopyToClipboard('tag31357');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2002546a0849af44134a44d3a4937423013c873a" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25941444627" target="_blank">2026-05-15 21:07:12</a></td></tr>
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
