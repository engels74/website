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
<tr><td><div id="tag19282" onclick="CopyToClipboard('tag19282');return false;" class="tag-decoration">nightly</div><div id="tag20261" onclick="CopyToClipboard('tag20261');return false;" class="tag-decoration">nightly-a59880e</div><div id="tag5740" onclick="CopyToClipboard('tag5740');return false;" class="tag-decoration">nightly-777db2015828fca63582d21b0e756fae21c1d80e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/a59880e66c6fe74ef6283c96344c654c82b87561" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354914900" target="_blank">2026-06-11 14:40:55</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag5647" onclick="CopyToClipboard('tag5647');return false;" class="tag-decoration">release</div><div id="tag32484" onclick="CopyToClipboard('tag32484');return false;" class="tag-decoration">release-54d73ad</div><div id="tag14974" onclick="CopyToClipboard('tag14974');return false;" class="tag-decoration">release-5.0.3</div><div id="tag8341" onclick="CopyToClipboard('tag8341');return false;" class="tag-decoration">release-v5</div><div id="tag13780" onclick="CopyToClipboard('tag13780');return false;" class="tag-decoration">release-v5.0</div><div id="tag9408" onclick="CopyToClipboard('tag9408');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/54d73addb8fc3a44795e8c69778aba56b83e6c9a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27276007223" target="_blank">2026-06-10 12:24:22</a></td></tr>
<tr><td><div id="tag14075" onclick="CopyToClipboard('tag14075');return false;" class="tag-decoration">testing</div><div id="tag16413" onclick="CopyToClipboard('tag16413');return false;" class="tag-decoration">testing-1b1942e</div><div id="tag11086" onclick="CopyToClipboard('tag11086');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag11874" onclick="CopyToClipboard('tag11874');return false;" class="tag-decoration">testing-v5</div><div id="tag4508" onclick="CopyToClipboard('tag4508');return false;" class="tag-decoration">testing-v5.0</div><div id="tag32183" onclick="CopyToClipboard('tag32183');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b1942e349033b72b39f15958dc0694493b2d37d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354916499" target="_blank">2026-06-11 14:40:59</a></td></tr>
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
