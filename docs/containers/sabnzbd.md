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
<tr><td><div id="tag20311" onclick="CopyToClipboard('tag20311');return false;" class="tag-decoration">nightly</div><div id="tag21561" onclick="CopyToClipboard('tag21561');return false;" class="tag-decoration">nightly-3bdf815</div><div id="tag2030" onclick="CopyToClipboard('tag2030');return false;" class="tag-decoration">nightly-cc61dc974b383e5bce04746274407448b6d0443e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/3bdf8156f92656e154410efb4d2bc810e46b0368" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26527216270" target="_blank">2026-05-27 17:22:29</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag27563" onclick="CopyToClipboard('tag27563');return false;" class="tag-decoration">release</div><div id="tag30414" onclick="CopyToClipboard('tag30414');return false;" class="tag-decoration">release-3577c35</div><div id="tag29344" onclick="CopyToClipboard('tag29344');return false;" class="tag-decoration">release-5.0.3</div><div id="tag11449" onclick="CopyToClipboard('tag11449');return false;" class="tag-decoration">release-v5</div><div id="tag3086" onclick="CopyToClipboard('tag3086');return false;" class="tag-decoration">release-v5.0</div><div id="tag5390" onclick="CopyToClipboard('tag5390');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3577c35caa29187d2d76ee36cad710fba3e90548" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26363856550" target="_blank">2026-05-24 14:26:18</a></td></tr>
<tr><td><div id="tag11075" onclick="CopyToClipboard('tag11075');return false;" class="tag-decoration">testing</div><div id="tag27709" onclick="CopyToClipboard('tag27709');return false;" class="tag-decoration">testing-9e0e5ab</div><div id="tag22094" onclick="CopyToClipboard('tag22094');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag26006" onclick="CopyToClipboard('tag26006');return false;" class="tag-decoration">testing-v5</div><div id="tag27091" onclick="CopyToClipboard('tag27091');return false;" class="tag-decoration">testing-v5.0</div><div id="tag20740" onclick="CopyToClipboard('tag20740');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/9e0e5abe127f87f579be820d0353c0ce0c1f4762" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26363856297" target="_blank">2026-05-24 14:26:17</a></td></tr>
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
