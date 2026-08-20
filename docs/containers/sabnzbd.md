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
<tr><td><div id="tag28675" onclick="CopyToClipboard('tag28675');return false;" class="tag-decoration">nightly</div><div id="tag30839" onclick="CopyToClipboard('tag30839');return false;" class="tag-decoration">nightly-e59781b</div><div id="tag27808" onclick="CopyToClipboard('tag27808');return false;" class="tag-decoration">nightly-21d639bf5ff898e05dd48ee08ca76b63e20046a5</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e59781b3a9adf81b00fc3a381803f258439d1acb" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32326594708" target="_blank">2026-08-20 02:59:12</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag6935" onclick="CopyToClipboard('tag6935');return false;" class="tag-decoration">release</div><div id="tag6989" onclick="CopyToClipboard('tag6989');return false;" class="tag-decoration">release-db59e20</div><div id="tag15183" onclick="CopyToClipboard('tag15183');return false;" class="tag-decoration">release-5.1.1</div><div id="tag17361" onclick="CopyToClipboard('tag17361');return false;" class="tag-decoration">release-v5</div><div id="tag4929" onclick="CopyToClipboard('tag4929');return false;" class="tag-decoration">release-v5.1</div><div id="tag23796" onclick="CopyToClipboard('tag23796');return false;" class="tag-decoration">release-v5.1.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/db59e2014720f7b35c0aa31c55fabd20513d3368" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32161076498" target="_blank">2026-08-18 16:34:58</a></td></tr>
<tr><td><div id="tag2358" onclick="CopyToClipboard('tag2358');return false;" class="tag-decoration">testing</div><div id="tag14385" onclick="CopyToClipboard('tag14385');return false;" class="tag-decoration">testing-fa0d47a</div><div id="tag26695" onclick="CopyToClipboard('tag26695');return false;" class="tag-decoration">testing-5.1.1</div><div id="tag31684" onclick="CopyToClipboard('tag31684');return false;" class="tag-decoration">testing-v5</div><div id="tag10285" onclick="CopyToClipboard('tag10285');return false;" class="tag-decoration">testing-v5.1</div><div id="tag31099" onclick="CopyToClipboard('tag31099');return false;" class="tag-decoration">testing-v5.1.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/fa0d47a2eebc3136ae59abc309f798b5a7a1b0e4" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32161074185" target="_blank">2026-08-18 16:34:54</a></td></tr>
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
