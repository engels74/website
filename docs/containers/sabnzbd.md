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
<tr><td><div id="tag4741" onclick="CopyToClipboard('tag4741');return false;" class="tag-decoration">nightly</div><div id="tag31581" onclick="CopyToClipboard('tag31581');return false;" class="tag-decoration">nightly-d005ae5</div><div id="tag5787" onclick="CopyToClipboard('tag5787');return false;" class="tag-decoration">nightly-e929a0c6b66cb6336d60e08ed052b2c0a3ac6ef8</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d005ae5dcd6847cafc23c7d557a45f327aa0b0b3" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596529066" target="_blank">2026-07-02 14:09:16</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag6118" onclick="CopyToClipboard('tag6118');return false;" class="tag-decoration">release</div><div id="tag21936" onclick="CopyToClipboard('tag21936');return false;" class="tag-decoration">release-b30cf3c</div><div id="tag23397" onclick="CopyToClipboard('tag23397');return false;" class="tag-decoration">release-5.0.4</div><div id="tag6162" onclick="CopyToClipboard('tag6162');return false;" class="tag-decoration">release-v5</div><div id="tag1434" onclick="CopyToClipboard('tag1434');return false;" class="tag-decoration">release-v5.0</div><div id="tag11042" onclick="CopyToClipboard('tag11042');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/b30cf3c8436673dc4b51fa0315c11553e8c8fac3" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28443343553" target="_blank">2026-06-30 12:12:17</a></td></tr>
<tr><td><div id="tag12665" onclick="CopyToClipboard('tag12665');return false;" class="tag-decoration">testing</div><div id="tag10581" onclick="CopyToClipboard('tag10581');return false;" class="tag-decoration">testing-870b377</div><div id="tag13212" onclick="CopyToClipboard('tag13212');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag5756" onclick="CopyToClipboard('tag5756');return false;" class="tag-decoration">testing-v5</div><div id="tag30383" onclick="CopyToClipboard('tag30383');return false;" class="tag-decoration">testing-v5.0</div><div id="tag18274" onclick="CopyToClipboard('tag18274');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/870b377c1295fdbbf529f0a4b1273c6b13c6f2ba" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28443343320" target="_blank">2026-06-30 12:12:17</a></td></tr>
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
