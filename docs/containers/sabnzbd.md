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
<tr><td><div id="tag15858" onclick="CopyToClipboard('tag15858');return false;" class="tag-decoration">nightly</div><div id="tag16428" onclick="CopyToClipboard('tag16428');return false;" class="tag-decoration">nightly-f7f94c8</div><div id="tag16768" onclick="CopyToClipboard('tag16768');return false;" class="tag-decoration">nightly-7a7201157d0c9acbbcc808f86bfcc33457e9564a</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f7f94c84547bb3fdb68001a05b15fa2f02ed6fc3" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/36243046406" target="_blank">2026-09-26 12:47:38</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag15553" onclick="CopyToClipboard('tag15553');return false;" class="tag-decoration">release</div><div id="tag1311" onclick="CopyToClipboard('tag1311');return false;" class="tag-decoration">release-7f49c81</div><div id="tag328" onclick="CopyToClipboard('tag328');return false;" class="tag-decoration">release-5.1.3</div><div id="tag26194" onclick="CopyToClipboard('tag26194');return false;" class="tag-decoration">release-v5</div><div id="tag31178" onclick="CopyToClipboard('tag31178');return false;" class="tag-decoration">release-v5.1</div><div id="tag2354" onclick="CopyToClipboard('tag2354');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7f49c8193cfd6e4bfb7d1d5f6ec8325d3ab09c27" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482526229" target="_blank">2026-09-10 13:25:12</a></td></tr>
<tr><td><div id="tag22297" onclick="CopyToClipboard('tag22297');return false;" class="tag-decoration">testing</div><div id="tag10357" onclick="CopyToClipboard('tag10357');return false;" class="tag-decoration">testing-ffe78cf</div><div id="tag22352" onclick="CopyToClipboard('tag22352');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag20742" onclick="CopyToClipboard('tag20742');return false;" class="tag-decoration">testing-v5</div><div id="tag16377" onclick="CopyToClipboard('tag16377');return false;" class="tag-decoration">testing-v5.1</div><div id="tag10308" onclick="CopyToClipboard('tag10308');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ffe78cf751803bd92188cb006e353d499184f818" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482510601" target="_blank">2026-09-10 13:25:03</a></td></tr>
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
