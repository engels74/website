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
<tr><td><div id="tag30376" onclick="CopyToClipboard('tag30376');return false;" class="tag-decoration">nightly</div><div id="tag3279" onclick="CopyToClipboard('tag3279');return false;" class="tag-decoration">nightly-524ce70</div><div id="tag15228" onclick="CopyToClipboard('tag15228');return false;" class="tag-decoration">nightly-d3f691e695f9c3a2065c9fc12eb22731ec30c673</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/524ce70d27e27f38576ec688031f6cf7c4e45fb5" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34088318286" target="_blank">2026-09-07 05:50:05</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag23859" onclick="CopyToClipboard('tag23859');return false;" class="tag-decoration">release</div><div id="tag26204" onclick="CopyToClipboard('tag26204');return false;" class="tag-decoration">release-20eb037</div><div id="tag16738" onclick="CopyToClipboard('tag16738');return false;" class="tag-decoration">release-5.1.2</div><div id="tag29091" onclick="CopyToClipboard('tag29091');return false;" class="tag-decoration">release-v5</div><div id="tag11992" onclick="CopyToClipboard('tag11992');return false;" class="tag-decoration">release-v5.1</div><div id="tag24353" onclick="CopyToClipboard('tag24353');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/20eb037ae7e9a857774d5d9beecfa51d2fded6f7" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33969812936" target="_blank">2026-09-05 13:45:18</a></td></tr>
<tr><td><div id="tag152" onclick="CopyToClipboard('tag152');return false;" class="tag-decoration">testing</div><div id="tag17336" onclick="CopyToClipboard('tag17336');return false;" class="tag-decoration">testing-fc03f0f</div><div id="tag6964" onclick="CopyToClipboard('tag6964');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag22178" onclick="CopyToClipboard('tag22178');return false;" class="tag-decoration">testing-v5</div><div id="tag7600" onclick="CopyToClipboard('tag7600');return false;" class="tag-decoration">testing-v5.1</div><div id="tag18739" onclick="CopyToClipboard('tag18739');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/fc03f0fa807a0aae7ff1c8e27d692f150745a6bb" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33969811147" target="_blank">2026-09-05 13:45:16</a></td></tr>
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
