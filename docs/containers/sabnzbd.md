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
<tr><td><div id="tag31673" onclick="CopyToClipboard('tag31673');return false;" class="tag-decoration">nightly</div><div id="tag23265" onclick="CopyToClipboard('tag23265');return false;" class="tag-decoration">nightly-3263536</div><div id="tag18675" onclick="CopyToClipboard('tag18675');return false;" class="tag-decoration">nightly-80840ce74356c0875b0701b5768f0789315fffa8</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/3263536c767c50d104ee452b65b28340585afb65" target="_blank">ci: point at engels74/base-image@workflows</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25881620015" target="_blank">2026-05-14 19:43:19</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20440" onclick="CopyToClipboard('tag20440');return false;" class="tag-decoration">release</div><div id="tag26838" onclick="CopyToClipboard('tag26838');return false;" class="tag-decoration">release-8cf5da7</div><div id="tag15167" onclick="CopyToClipboard('tag15167');return false;" class="tag-decoration">release-5.0.2</div><div id="tag16512" onclick="CopyToClipboard('tag16512');return false;" class="tag-decoration">release-v5</div><div id="tag6624" onclick="CopyToClipboard('tag6624');return false;" class="tag-decoration">release-v5.0</div><div id="tag7863" onclick="CopyToClipboard('tag7863');return false;" class="tag-decoration">release-v5.0.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8cf5da726675a249f35840f39e57d601dde6ca98" target="_blank">ci: point at engels74/base-image@workflows</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25881622029" target="_blank">2026-05-14 19:43:21</a></td></tr>
<tr><td><div id="tag21790" onclick="CopyToClipboard('tag21790');return false;" class="tag-decoration">testing</div><div id="tag22658" onclick="CopyToClipboard('tag22658');return false;" class="tag-decoration">testing-896b7d5</div><div id="tag16750" onclick="CopyToClipboard('tag16750');return false;" class="tag-decoration">testing-5.0.2</div><div id="tag21319" onclick="CopyToClipboard('tag21319');return false;" class="tag-decoration">testing-v5</div><div id="tag8514" onclick="CopyToClipboard('tag8514');return false;" class="tag-decoration">testing-v5.0</div><div id="tag6284" onclick="CopyToClipboard('tag6284');return false;" class="tag-decoration">testing-v5.0.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/896b7d58cabe533f15002a045bf1e701fc43e434" target="_blank">Version update: 5.0.1 => 5.0.2</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25879715545" target="_blank">2026-05-14 19:04:21</a></td></tr>
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
