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
<tr><td><div id="tag20829" onclick="CopyToClipboard('tag20829');return false;" class="tag-decoration">nightly</div><div id="tag18653" onclick="CopyToClipboard('tag18653');return false;" class="tag-decoration">nightly-e011327</div><div id="tag25543" onclick="CopyToClipboard('tag25543');return false;" class="tag-decoration">nightly-80840ce74356c0875b0701b5768f0789315fffa8</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e011327af0b7dcbf9af88a24b9a68794e3abae25" target="_blank">Version update: 2184964d7877e0fddee0fd0421e6c21fd38ceae7 => 80840ce74356c0875b0701b5768f0789315fffa8</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25825638479" target="_blank">2026-05-13 20:49:46</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15293" onclick="CopyToClipboard('tag15293');return false;" class="tag-decoration">release</div><div id="tag15175" onclick="CopyToClipboard('tag15175');return false;" class="tag-decoration">release-2669f97</div><div id="tag18841" onclick="CopyToClipboard('tag18841');return false;" class="tag-decoration">release-5.0.2</div><div id="tag4167" onclick="CopyToClipboard('tag4167');return false;" class="tag-decoration">release-v5</div><div id="tag24818" onclick="CopyToClipboard('tag24818');return false;" class="tag-decoration">release-v5.0</div><div id="tag9401" onclick="CopyToClipboard('tag9401');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2669f974632e92a0894f3a7b73b2782ac1eda432" target="_blank">Version update: 5.0.1 => 5.0.2</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25879713837" target="_blank">2026-05-14 19:04:19</a></td></tr>
<tr><td><div id="tag1576" onclick="CopyToClipboard('tag1576');return false;" class="tag-decoration">testing</div><div id="tag26460" onclick="CopyToClipboard('tag26460');return false;" class="tag-decoration">testing-896b7d5</div><div id="tag32584" onclick="CopyToClipboard('tag32584');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag22713" onclick="CopyToClipboard('tag22713');return false;" class="tag-decoration">testing-v5</div><div id="tag28504" onclick="CopyToClipboard('tag28504');return false;" class="tag-decoration">testing-v5.0</div><div id="tag16989" onclick="CopyToClipboard('tag16989');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/896b7d58cabe533f15002a045bf1e701fc43e434" target="_blank">Version update: 5.0.1 => 5.0.2</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25879715545" target="_blank">2026-05-14 19:04:21</a></td></tr>
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
