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
<tr><td><div id="tag2105" onclick="CopyToClipboard('tag2105');return false;" class="tag-decoration">nightly</div><div id="tag25961" onclick="CopyToClipboard('tag25961');return false;" class="tag-decoration">nightly-40d0c7b</div><div id="tag9734" onclick="CopyToClipboard('tag9734');return false;" class="tag-decoration">nightly-011794142251a9669c40b21a02e855f82d1ae043</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/40d0c7ba384d41d3dd6eb5cc4d0a9deaa84552b2" target="_blank">Version update: 004e4e68ebe2946b443891b7e73a0d1d49939bfa => 011794142251a9669c40b21a02e855f82d1ae043</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24322220166" target="_blank">2026-04-13 02:00:37</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26775" onclick="CopyToClipboard('tag26775');return false;" class="tag-decoration">release</div><div id="tag18920" onclick="CopyToClipboard('tag18920');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag10963" onclick="CopyToClipboard('tag10963');return false;" class="tag-decoration">release-4.5.5</div><div id="tag21940" onclick="CopyToClipboard('tag21940');return false;" class="tag-decoration">release-v4</div><div id="tag8040" onclick="CopyToClipboard('tag8040');return false;" class="tag-decoration">release-v4.5</div><div id="tag32036" onclick="CopyToClipboard('tag32036');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag3568" onclick="CopyToClipboard('tag3568');return false;" class="tag-decoration">testing</div><div id="tag13202" onclick="CopyToClipboard('tag13202');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag32049" onclick="CopyToClipboard('tag32049');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag29965" onclick="CopyToClipboard('tag29965');return false;" class="tag-decoration">testing-v4</div><div id="tag14161" onclick="CopyToClipboard('tag14161');return false;" class="tag-decoration">testing-v4.5</div><div id="tag7219" onclick="CopyToClipboard('tag7219');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
