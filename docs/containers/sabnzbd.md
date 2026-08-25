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
<tr><td><div id="tag18223" onclick="CopyToClipboard('tag18223');return false;" class="tag-decoration">nightly</div><div id="tag13898" onclick="CopyToClipboard('tag13898');return false;" class="tag-decoration">nightly-07a74a2</div><div id="tag26813" onclick="CopyToClipboard('tag26813');return false;" class="tag-decoration">nightly-f498147189f325393c5b762279b8cf708aa37e56</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/07a74a2f676ca7cd05828130c1b266d7be8d844d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32842740996" target="_blank">2026-08-25 11:31:14</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag30489" onclick="CopyToClipboard('tag30489');return false;" class="tag-decoration">release</div><div id="tag5287" onclick="CopyToClipboard('tag5287');return false;" class="tag-decoration">release-87f6728</div><div id="tag19547" onclick="CopyToClipboard('tag19547');return false;" class="tag-decoration">release-5.1.1</div><div id="tag23389" onclick="CopyToClipboard('tag23389');return false;" class="tag-decoration">release-v5</div><div id="tag2014" onclick="CopyToClipboard('tag2014');return false;" class="tag-decoration">release-v5.1</div><div id="tag23916" onclick="CopyToClipboard('tag23916');return false;" class="tag-decoration">release-v5.1.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/87f6728be54de4685822ca23f362b10fc05add0c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381402735" target="_blank">2026-08-20 14:38:57</a></td></tr>
<tr><td><div id="tag2631" onclick="CopyToClipboard('tag2631');return false;" class="tag-decoration">testing</div><div id="tag6397" onclick="CopyToClipboard('tag6397');return false;" class="tag-decoration">testing-e417274</div><div id="tag5394" onclick="CopyToClipboard('tag5394');return false;" class="tag-decoration">testing-5.1.1</div><div id="tag11883" onclick="CopyToClipboard('tag11883');return false;" class="tag-decoration">testing-v5</div><div id="tag18665" onclick="CopyToClipboard('tag18665');return false;" class="tag-decoration">testing-v5.1</div><div id="tag7792" onclick="CopyToClipboard('tag7792');return false;" class="tag-decoration">testing-v5.1.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e417274da1817bfeeeadbb99d597f90b9d06a636" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381393649" target="_blank">2026-08-20 14:38:53</a></td></tr>
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
