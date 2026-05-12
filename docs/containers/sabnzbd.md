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
<tr><td><div id="tag1469" onclick="CopyToClipboard('tag1469');return false;" class="tag-decoration">nightly</div><div id="tag20627" onclick="CopyToClipboard('tag20627');return false;" class="tag-decoration">nightly-d3bc18f</div><div id="tag17463" onclick="CopyToClipboard('tag17463');return false;" class="tag-decoration">nightly-90798e5e4dcbd2e45bc0aa36f95de482e08b8cea</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d3bc18fcb877ea7bb12bab9202c3c4c4d1c6fa76" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25713907722" target="_blank">2026-05-12 04:44:32</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag23163" onclick="CopyToClipboard('tag23163');return false;" class="tag-decoration">release</div><div id="tag28490" onclick="CopyToClipboard('tag28490');return false;" class="tag-decoration">release-f6d19f7</div><div id="tag25406" onclick="CopyToClipboard('tag25406');return false;" class="tag-decoration">release-5.0.1</div><div id="tag13411" onclick="CopyToClipboard('tag13411');return false;" class="tag-decoration">release-v5</div><div id="tag17467" onclick="CopyToClipboard('tag17467');return false;" class="tag-decoration">release-v5.0</div><div id="tag27770" onclick="CopyToClipboard('tag27770');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f6d19f79496d9dbce75a040beca45c30ecbc9fb5" target="_blank">Upstream update: alpinevpn-4699fa7 => alpinevpn-f4e73db</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25605042893" target="_blank">2026-05-09 15:43:10</a></td></tr>
<tr><td><div id="tag2275" onclick="CopyToClipboard('tag2275');return false;" class="tag-decoration">testing</div><div id="tag28470" onclick="CopyToClipboard('tag28470');return false;" class="tag-decoration">testing-b6bc765</div><div id="tag5782" onclick="CopyToClipboard('tag5782');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag25258" onclick="CopyToClipboard('tag25258');return false;" class="tag-decoration">testing-v5</div><div id="tag8567" onclick="CopyToClipboard('tag8567');return false;" class="tag-decoration">testing-v5.0</div><div id="tag3148" onclick="CopyToClipboard('tag3148');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b6bc7659612c8e05b6e39587a09d2ac4aba4c770" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25713913622" target="_blank">2026-05-12 04:44:44</a></td></tr>
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
