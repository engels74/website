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
<tr><td><div id="tag23129" onclick="CopyToClipboard('tag23129');return false;" class="tag-decoration">nightly</div><div id="tag28548" onclick="CopyToClipboard('tag28548');return false;" class="tag-decoration">nightly-36b38ca</div><div id="tag22539" onclick="CopyToClipboard('tag22539');return false;" class="tag-decoration">nightly-8069361faaf6f00d384af990634538c28bcec619</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/36b38ca3357ed5ef0f961301b727dd4a9d85193f" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25941445796" target="_blank">2026-05-15 21:07:14</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag8365" onclick="CopyToClipboard('tag8365');return false;" class="tag-decoration">release</div><div id="tag9368" onclick="CopyToClipboard('tag9368');return false;" class="tag-decoration">release-6b59852</div><div id="tag20736" onclick="CopyToClipboard('tag20736');return false;" class="tag-decoration">release-5.0.3</div><div id="tag11982" onclick="CopyToClipboard('tag11982');return false;" class="tag-decoration">release-v5</div><div id="tag31758" onclick="CopyToClipboard('tag31758');return false;" class="tag-decoration">release-v5.0</div><div id="tag1233" onclick="CopyToClipboard('tag1233');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/6b59852fcbb08ef8cbf9b183bb25ff7450e5bbd7" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25965096351" target="_blank">2026-05-16 15:00:04</a></td></tr>
<tr><td><div id="tag26477" onclick="CopyToClipboard('tag26477');return false;" class="tag-decoration">testing</div><div id="tag14886" onclick="CopyToClipboard('tag14886');return false;" class="tag-decoration">testing-2002546</div><div id="tag9263" onclick="CopyToClipboard('tag9263');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag25999" onclick="CopyToClipboard('tag25999');return false;" class="tag-decoration">testing-v5</div><div id="tag5248" onclick="CopyToClipboard('tag5248');return false;" class="tag-decoration">testing-v5.0</div><div id="tag28179" onclick="CopyToClipboard('tag28179');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2002546a0849af44134a44d3a4937423013c873a" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25941444627" target="_blank">2026-05-15 21:07:12</a></td></tr>
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
