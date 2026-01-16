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
<tr><td><div id="tag17964" onclick="CopyToClipboard('tag17964');return false;" class="tag-decoration">nightly</div><div id="tag7266" onclick="CopyToClipboard('tag7266');return false;" class="tag-decoration">nightly-abc8b20</div><div id="tag25833" onclick="CopyToClipboard('tag25833');return false;" class="tag-decoration">nightly-df1c0915d07982546e282b2b52354a49cde993ba</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/abc8b20b7359af8f04b176afe36ebad128440694" target="_blank">Upstream update: alpinevpn-897a0b9 => alpinevpn-c74319d</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21074855419" target="_blank">2026-01-16 17:19:28</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20062" onclick="CopyToClipboard('tag20062');return false;" class="tag-decoration">release</div><div id="tag2662" onclick="CopyToClipboard('tag2662');return false;" class="tag-decoration">release-1b3137f</div><div id="tag3831" onclick="CopyToClipboard('tag3831');return false;" class="tag-decoration">release-4.5.5</div><div id="tag24192" onclick="CopyToClipboard('tag24192');return false;" class="tag-decoration">release-v4</div><div id="tag13416" onclick="CopyToClipboard('tag13416');return false;" class="tag-decoration">release-v4.5</div><div id="tag14412" onclick="CopyToClipboard('tag14412');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b3137fb6fa6a24b66fbb6e414ded10e059fbb35" target="_blank">Upstream update: alpinevpn-897a0b9 => alpinevpn-c74319d</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21074856285" target="_blank">2026-01-16 17:19:30</a></td></tr>
<tr><td><div id="tag7433" onclick="CopyToClipboard('tag7433');return false;" class="tag-decoration">testing</div><div id="tag10616" onclick="CopyToClipboard('tag10616');return false;" class="tag-decoration">testing-21558e8</div><div id="tag1613" onclick="CopyToClipboard('tag1613');return false;" class="tag-decoration">testing-4.6.0Beta2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/21558e87b4d17aeb3470d8fffcd0b830c1009944" target="_blank">Upstream update: alpinevpn-897a0b9 => alpinevpn-c74319d</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21073193356" target="_blank">2026-01-16 16:20:03</a></td></tr>
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
