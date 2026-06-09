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
<tr><td><div id="tag25776" onclick="CopyToClipboard('tag25776');return false;" class="tag-decoration">nightly</div><div id="tag9745" onclick="CopyToClipboard('tag9745');return false;" class="tag-decoration">nightly-ada2f5a</div><div id="tag19818" onclick="CopyToClipboard('tag19818');return false;" class="tag-decoration">nightly-afae687b6ad1944158d8cd990b5aa0befb8ca502</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/ada2f5aa0d979c20f3614d7b2ad0c6dfc3584a9f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27216160786" target="_blank">2026-06-09 15:15:02</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag25969" onclick="CopyToClipboard('tag25969');return false;" class="tag-decoration">release</div><div id="tag12256" onclick="CopyToClipboard('tag12256');return false;" class="tag-decoration">release-bcf36ce</div><div id="tag150" onclick="CopyToClipboard('tag150');return false;" class="tag-decoration">release-5.0.3</div><div id="tag30912" onclick="CopyToClipboard('tag30912');return false;" class="tag-decoration">release-v5</div><div id="tag22388" onclick="CopyToClipboard('tag22388');return false;" class="tag-decoration">release-v5.0</div><div id="tag4729" onclick="CopyToClipboard('tag4729');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/bcf36cef7a746f9ef94e609755b9263b9a747688" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710781564" target="_blank">2026-05-31 11:01:09</a></td></tr>
<tr><td><div id="tag4145" onclick="CopyToClipboard('tag4145');return false;" class="tag-decoration">testing</div><div id="tag27389" onclick="CopyToClipboard('tag27389');return false;" class="tag-decoration">testing-009193c</div><div id="tag13943" onclick="CopyToClipboard('tag13943');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag5962" onclick="CopyToClipboard('tag5962');return false;" class="tag-decoration">testing-v5</div><div id="tag15607" onclick="CopyToClipboard('tag15607');return false;" class="tag-decoration">testing-v5.0</div><div id="tag21316" onclick="CopyToClipboard('tag21316');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/009193c9e6c31de8f8cdff399b7f16aa7f6beaaf" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26710782493" target="_blank">2026-05-31 11:01:11</a></td></tr>
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
