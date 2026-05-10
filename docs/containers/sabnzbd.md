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
<tr><td><div id="tag1061" onclick="CopyToClipboard('tag1061');return false;" class="tag-decoration">nightly</div><div id="tag5324" onclick="CopyToClipboard('tag5324');return false;" class="tag-decoration">nightly-7f007af</div><div id="tag28052" onclick="CopyToClipboard('tag28052');return false;" class="tag-decoration">nightly-7abb39d02d7833cc929e1379b0be6e9bfe7d5bd7</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7f007af68503a81807b6a84a346a3333e9b8a963" target="_blank">Version update: 2668f1cd267ce13722c9f695337a8f7d134f3fba => 7abb39d02d7833cc929e1379b0be6e9bfe7d5bd7</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25626509091" target="_blank">2026-05-10 10:36:11</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag21225" onclick="CopyToClipboard('tag21225');return false;" class="tag-decoration">release</div><div id="tag10014" onclick="CopyToClipboard('tag10014');return false;" class="tag-decoration">release-f6d19f7</div><div id="tag1612" onclick="CopyToClipboard('tag1612');return false;" class="tag-decoration">release-5.0.1</div><div id="tag32703" onclick="CopyToClipboard('tag32703');return false;" class="tag-decoration">release-v5</div><div id="tag28237" onclick="CopyToClipboard('tag28237');return false;" class="tag-decoration">release-v5.0</div><div id="tag6835" onclick="CopyToClipboard('tag6835');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f6d19f79496d9dbce75a040beca45c30ecbc9fb5" target="_blank">Upstream update: alpinevpn-4699fa7 => alpinevpn-f4e73db</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25605042893" target="_blank">2026-05-09 15:43:10</a></td></tr>
<tr><td><div id="tag17394" onclick="CopyToClipboard('tag17394');return false;" class="tag-decoration">testing</div><div id="tag9970" onclick="CopyToClipboard('tag9970');return false;" class="tag-decoration">testing-3f2759d</div><div id="tag29404" onclick="CopyToClipboard('tag29404');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag25353" onclick="CopyToClipboard('tag25353');return false;" class="tag-decoration">testing-v5</div><div id="tag9330" onclick="CopyToClipboard('tag9330');return false;" class="tag-decoration">testing-v5.0</div><div id="tag26973" onclick="CopyToClipboard('tag26973');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3f2759dda3ec0b56e55f72fa6a82a4c141aa2462" target="_blank">Upstream update: alpinevpn-4699fa7 => alpinevpn-f4e73db</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25605043362" target="_blank">2026-05-09 15:43:12</a></td></tr>
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
