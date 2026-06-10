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
<tr><td><div id="tag16306" onclick="CopyToClipboard('tag16306');return false;" class="tag-decoration">nightly</div><div id="tag11048" onclick="CopyToClipboard('tag11048');return false;" class="tag-decoration">nightly-69002ca</div><div id="tag26746" onclick="CopyToClipboard('tag26746');return false;" class="tag-decoration">nightly-45aafe07744f12852e3731bd99e9f72064c47998</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/69002ca803f2f2f9e0d3f050a80b5684fc0ee3c8" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27276006989" target="_blank">2026-06-10 12:24:21</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag13113" onclick="CopyToClipboard('tag13113');return false;" class="tag-decoration">release</div><div id="tag21338" onclick="CopyToClipboard('tag21338');return false;" class="tag-decoration">release-54d73ad</div><div id="tag32147" onclick="CopyToClipboard('tag32147');return false;" class="tag-decoration">release-5.0.3</div><div id="tag32287" onclick="CopyToClipboard('tag32287');return false;" class="tag-decoration">release-v5</div><div id="tag27628" onclick="CopyToClipboard('tag27628');return false;" class="tag-decoration">release-v5.0</div><div id="tag24116" onclick="CopyToClipboard('tag24116');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/54d73addb8fc3a44795e8c69778aba56b83e6c9a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27276007223" target="_blank">2026-06-10 12:24:22</a></td></tr>
<tr><td><div id="tag2057" onclick="CopyToClipboard('tag2057');return false;" class="tag-decoration">testing</div><div id="tag2253" onclick="CopyToClipboard('tag2253');return false;" class="tag-decoration">testing-2b6b410</div><div id="tag2798" onclick="CopyToClipboard('tag2798');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag760" onclick="CopyToClipboard('tag760');return false;" class="tag-decoration">testing-v5</div><div id="tag30419" onclick="CopyToClipboard('tag30419');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23913" onclick="CopyToClipboard('tag23913');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b6b41012a29ae085439fbb836e930068761df8d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27276003719" target="_blank">2026-06-10 12:24:18</a></td></tr>
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
