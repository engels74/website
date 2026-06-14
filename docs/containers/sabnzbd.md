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
<tr><td><div id="tag32597" onclick="CopyToClipboard('tag32597');return false;" class="tag-decoration">nightly</div><div id="tag25124" onclick="CopyToClipboard('tag25124');return false;" class="tag-decoration">nightly-f590d96</div><div id="tag912" onclick="CopyToClipboard('tag912');return false;" class="tag-decoration">nightly-fee562d57f6f4e16e07ed882a8cb0f14e7fa2b23</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/f590d96294e243d7e0ee5c66a08d6e28cdf90a94" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27498167358" target="_blank">2026-06-14 12:00:31</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20808" onclick="CopyToClipboard('tag20808');return false;" class="tag-decoration">release</div><div id="tag23912" onclick="CopyToClipboard('tag23912');return false;" class="tag-decoration">release-746e018</div><div id="tag9769" onclick="CopyToClipboard('tag9769');return false;" class="tag-decoration">release-5.0.4</div><div id="tag10856" onclick="CopyToClipboard('tag10856');return false;" class="tag-decoration">release-v5</div><div id="tag7814" onclick="CopyToClipboard('tag7814');return false;" class="tag-decoration">release-v5.0</div><div id="tag13455" onclick="CopyToClipboard('tag13455');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/746e018cd50910dae73acbd4ab2ae90183233d6c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354913378" target="_blank">2026-06-11 14:40:57</a></td></tr>
<tr><td><div id="tag3984" onclick="CopyToClipboard('tag3984');return false;" class="tag-decoration">testing</div><div id="tag29720" onclick="CopyToClipboard('tag29720');return false;" class="tag-decoration">testing-1b1942e</div><div id="tag16104" onclick="CopyToClipboard('tag16104');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag8245" onclick="CopyToClipboard('tag8245');return false;" class="tag-decoration">testing-v5</div><div id="tag19169" onclick="CopyToClipboard('tag19169');return false;" class="tag-decoration">testing-v5.0</div><div id="tag10793" onclick="CopyToClipboard('tag10793');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b1942e349033b72b39f15958dc0694493b2d37d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354916499" target="_blank">2026-06-11 14:40:59</a></td></tr>
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
