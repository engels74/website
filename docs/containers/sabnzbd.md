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
<tr><td><div id="tag3265" onclick="CopyToClipboard('tag3265');return false;" class="tag-decoration">nightly</div><div id="tag18032" onclick="CopyToClipboard('tag18032');return false;" class="tag-decoration">nightly-ddc3968</div><div id="tag4451" onclick="CopyToClipboard('tag4451');return false;" class="tag-decoration">nightly-8afb8a91e29aaf8fc319c2f370e2b2611167a5f5</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/ddc3968e941c5db6f0f602fac938d4f62f26c97e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979405999" target="_blank">2026-07-08 22:13:20</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag5128" onclick="CopyToClipboard('tag5128');return false;" class="tag-decoration">release</div><div id="tag18631" onclick="CopyToClipboard('tag18631');return false;" class="tag-decoration">release-5f895d5</div><div id="tag289" onclick="CopyToClipboard('tag289');return false;" class="tag-decoration">release-5.0.4</div><div id="tag10480" onclick="CopyToClipboard('tag10480');return false;" class="tag-decoration">release-v5</div><div id="tag5868" onclick="CopyToClipboard('tag5868');return false;" class="tag-decoration">release-v5.0</div><div id="tag32296" onclick="CopyToClipboard('tag32296');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5f895d55bff876b3ada4d917157eeb04ded7ccc4" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596533894" target="_blank">2026-07-02 14:09:19</a></td></tr>
<tr><td><div id="tag20356" onclick="CopyToClipboard('tag20356');return false;" class="tag-decoration">testing</div><div id="tag11169" onclick="CopyToClipboard('tag11169');return false;" class="tag-decoration">testing-4c71f05</div><div id="tag27099" onclick="CopyToClipboard('tag27099');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag10119" onclick="CopyToClipboard('tag10119');return false;" class="tag-decoration">testing-v5</div><div id="tag32586" onclick="CopyToClipboard('tag32586');return false;" class="tag-decoration">testing-v5.0</div><div id="tag19996" onclick="CopyToClipboard('tag19996');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4c71f05cc28313bfb31556bb9d28a2c7c7de987a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28596533446" target="_blank">2026-07-02 14:09:19</a></td></tr>
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
