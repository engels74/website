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
<tr><td><div id="tag14718" onclick="CopyToClipboard('tag14718');return false;" class="tag-decoration">nightly</div><div id="tag4024" onclick="CopyToClipboard('tag4024');return false;" class="tag-decoration">nightly-73e4059</div><div id="tag321" onclick="CopyToClipboard('tag321');return false;" class="tag-decoration">nightly-25d20f0f08ce2078402faf0e7b281db9ceb04643</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/73e4059aaf8b86a2165bfbba6fb3df67407c1d1a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26363855779" target="_blank">2026-05-24 14:26:16</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag31923" onclick="CopyToClipboard('tag31923');return false;" class="tag-decoration">release</div><div id="tag25321" onclick="CopyToClipboard('tag25321');return false;" class="tag-decoration">release-5d5cbe4</div><div id="tag25095" onclick="CopyToClipboard('tag25095');return false;" class="tag-decoration">release-5.0.3</div><div id="tag18403" onclick="CopyToClipboard('tag18403');return false;" class="tag-decoration">release-v5</div><div id="tag9244" onclick="CopyToClipboard('tag9244');return false;" class="tag-decoration">release-v5.0</div><div id="tag16826" onclick="CopyToClipboard('tag16826');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5d5cbe4f1453595a65a688585076e50490ae51cf" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26360697364" target="_blank">2026-05-24 12:02:16</a></td></tr>
<tr><td><div id="tag24555" onclick="CopyToClipboard('tag24555');return false;" class="tag-decoration">testing</div><div id="tag3231" onclick="CopyToClipboard('tag3231');return false;" class="tag-decoration">testing-9e0e5ab</div><div id="tag25090" onclick="CopyToClipboard('tag25090');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag13440" onclick="CopyToClipboard('tag13440');return false;" class="tag-decoration">testing-v5</div><div id="tag27122" onclick="CopyToClipboard('tag27122');return false;" class="tag-decoration">testing-v5.0</div><div id="tag3628" onclick="CopyToClipboard('tag3628');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/9e0e5abe127f87f579be820d0353c0ce0c1f4762" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26363856297" target="_blank">2026-05-24 14:26:17</a></td></tr>
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
