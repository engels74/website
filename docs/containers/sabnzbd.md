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
<tr><td><div id="tag1556" onclick="CopyToClipboard('tag1556');return false;" class="tag-decoration">nightly</div><div id="tag12798" onclick="CopyToClipboard('tag12798');return false;" class="tag-decoration">nightly-b812ddc</div><div id="tag2055" onclick="CopyToClipboard('tag2055');return false;" class="tag-decoration">nightly-44777dc3cf5bcebf175d9ee95c7e1965c4d714c8</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/b812ddcefa14cc90b53c5265d40241783a7c5b94" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424701426" target="_blank">2026-07-15 14:41:36</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20335" onclick="CopyToClipboard('tag20335');return false;" class="tag-decoration">release</div><div id="tag4805" onclick="CopyToClipboard('tag4805');return false;" class="tag-decoration">release-5cab8a0</div><div id="tag14896" onclick="CopyToClipboard('tag14896');return false;" class="tag-decoration">release-5.0.4</div><div id="tag8053" onclick="CopyToClipboard('tag8053');return false;" class="tag-decoration">release-v5</div><div id="tag13998" onclick="CopyToClipboard('tag13998');return false;" class="tag-decoration">release-v5.0</div><div id="tag10583" onclick="CopyToClipboard('tag10583');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5cab8a094ea2eda370354e3287e77da5efab3700" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29317186467" target="_blank">2026-07-14 08:12:12</a></td></tr>
<tr><td><div id="tag14644" onclick="CopyToClipboard('tag14644');return false;" class="tag-decoration">testing</div><div id="tag23019" onclick="CopyToClipboard('tag23019');return false;" class="tag-decoration">testing-8a80aca</div><div id="tag17245" onclick="CopyToClipboard('tag17245');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag4880" onclick="CopyToClipboard('tag4880');return false;" class="tag-decoration">testing-v5</div><div id="tag17497" onclick="CopyToClipboard('tag17497');return false;" class="tag-decoration">testing-v5.0</div><div id="tag27671" onclick="CopyToClipboard('tag27671');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8a80aca145642c4e9646450e02336a81a7c1684e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29317185232" target="_blank">2026-07-14 08:12:10</a></td></tr>
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
