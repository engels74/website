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
<tr><td><div id="tag1426" onclick="CopyToClipboard('tag1426');return false;" class="tag-decoration">nightly</div><div id="tag10160" onclick="CopyToClipboard('tag10160');return false;" class="tag-decoration">nightly-787d526</div><div id="tag14698" onclick="CopyToClipboard('tag14698');return false;" class="tag-decoration">nightly-6ff8aa7cef41d0494c6f107c3a642751d8f48b69</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/787d526f53257a53c08f28616ebb37bd0b5be01d" target="_blank">Version update: 011794142251a9669c40b21a02e855f82d1ae043 => 6ff8aa7cef41d0494c6f107c3a642751d8f48b69</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/24358469479" target="_blank">2026-04-13 17:54:23</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag31347" onclick="CopyToClipboard('tag31347');return false;" class="tag-decoration">release</div><div id="tag9318" onclick="CopyToClipboard('tag9318');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag22967" onclick="CopyToClipboard('tag22967');return false;" class="tag-decoration">release-4.5.5</div><div id="tag4712" onclick="CopyToClipboard('tag4712');return false;" class="tag-decoration">release-v4</div><div id="tag22096" onclick="CopyToClipboard('tag22096');return false;" class="tag-decoration">release-v4.5</div><div id="tag24406" onclick="CopyToClipboard('tag24406');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag11660" onclick="CopyToClipboard('tag11660');return false;" class="tag-decoration">testing</div><div id="tag3738" onclick="CopyToClipboard('tag3738');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag29900" onclick="CopyToClipboard('tag29900');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag23727" onclick="CopyToClipboard('tag23727');return false;" class="tag-decoration">testing-v4</div><div id="tag31836" onclick="CopyToClipboard('tag31836');return false;" class="tag-decoration">testing-v4.5</div><div id="tag9308" onclick="CopyToClipboard('tag9308');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
