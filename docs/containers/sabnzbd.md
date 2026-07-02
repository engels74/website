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
<tr><td><div id="tag2423" onclick="CopyToClipboard('tag2423');return false;" class="tag-decoration">nightly</div><div id="tag3291" onclick="CopyToClipboard('tag3291');return false;" class="tag-decoration">nightly-d005ae5</div><div id="tag16197" onclick="CopyToClipboard('tag16197');return false;" class="tag-decoration">nightly-e929a0c6b66cb6336d60e08ed052b2c0a3ac6ef8</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d005ae5dcd6847cafc23c7d557a45f327aa0b0b3" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596529066" target="_blank">2026-07-02 14:09:16</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag12699" onclick="CopyToClipboard('tag12699');return false;" class="tag-decoration">release</div><div id="tag27965" onclick="CopyToClipboard('tag27965');return false;" class="tag-decoration">release-5f895d5</div><div id="tag25026" onclick="CopyToClipboard('tag25026');return false;" class="tag-decoration">release-5.0.4</div><div id="tag10911" onclick="CopyToClipboard('tag10911');return false;" class="tag-decoration">release-v5</div><div id="tag6269" onclick="CopyToClipboard('tag6269');return false;" class="tag-decoration">release-v5.0</div><div id="tag1596" onclick="CopyToClipboard('tag1596');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f895d55bff876b3ada4d917157eeb04ded7ccc4" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596533894" target="_blank">2026-07-02 14:09:19</a></td></tr>
<tr><td><div id="tag6153" onclick="CopyToClipboard('tag6153');return false;" class="tag-decoration">testing</div><div id="tag19259" onclick="CopyToClipboard('tag19259');return false;" class="tag-decoration">testing-4c71f05</div><div id="tag11895" onclick="CopyToClipboard('tag11895');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag11783" onclick="CopyToClipboard('tag11783');return false;" class="tag-decoration">testing-v5</div><div id="tag16765" onclick="CopyToClipboard('tag16765');return false;" class="tag-decoration">testing-v5.0</div><div id="tag3709" onclick="CopyToClipboard('tag3709');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4c71f05cc28313bfb31556bb9d28a2c7c7de987a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596533446" target="_blank">2026-07-02 14:09:19</a></td></tr>
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
