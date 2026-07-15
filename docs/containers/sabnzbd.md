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
<tr><td><div id="tag4660" onclick="CopyToClipboard('tag4660');return false;" class="tag-decoration">nightly</div><div id="tag3046" onclick="CopyToClipboard('tag3046');return false;" class="tag-decoration">nightly-b812ddc</div><div id="tag24917" onclick="CopyToClipboard('tag24917');return false;" class="tag-decoration">nightly-44777dc3cf5bcebf175d9ee95c7e1965c4d714c8</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/b812ddcefa14cc90b53c5265d40241783a7c5b94" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424701426" target="_blank">2026-07-15 14:41:36</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag917" onclick="CopyToClipboard('tag917');return false;" class="tag-decoration">release</div><div id="tag8853" onclick="CopyToClipboard('tag8853');return false;" class="tag-decoration">release-22b6faf</div><div id="tag4560" onclick="CopyToClipboard('tag4560');return false;" class="tag-decoration">release-5.0.4</div><div id="tag10216" onclick="CopyToClipboard('tag10216');return false;" class="tag-decoration">release-v5</div><div id="tag28802" onclick="CopyToClipboard('tag28802');return false;" class="tag-decoration">release-v5.0</div><div id="tag19560" onclick="CopyToClipboard('tag19560');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/22b6fafa41c0542d04f69e85ff0d1141ea314f3d" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424697585" target="_blank">2026-07-15 14:41:34</a></td></tr>
<tr><td><div id="tag32293" onclick="CopyToClipboard('tag32293');return false;" class="tag-decoration">testing</div><div id="tag1081" onclick="CopyToClipboard('tag1081');return false;" class="tag-decoration">testing-1e4ca17</div><div id="tag12233" onclick="CopyToClipboard('tag12233');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag19964" onclick="CopyToClipboard('tag19964');return false;" class="tag-decoration">testing-v5</div><div id="tag3756" onclick="CopyToClipboard('tag3756');return false;" class="tag-decoration">testing-v5.0</div><div id="tag10304" onclick="CopyToClipboard('tag10304');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1e4ca177af138b56d90a850f38d042d76b5b9471" target="_blank">fix: move user bundle markers to user-bundles.d for s6-overlay >= 3.2.3.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29424701638" target="_blank">2026-07-15 14:41:38</a></td></tr>
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
