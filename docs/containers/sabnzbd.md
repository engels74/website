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
<tr><td><div id="tag20202" onclick="CopyToClipboard('tag20202');return false;" class="tag-decoration">nightly</div><div id="tag6045" onclick="CopyToClipboard('tag6045');return false;" class="tag-decoration">nightly-fedddea</div><div id="tag22717" onclick="CopyToClipboard('tag22717');return false;" class="tag-decoration">nightly-594e303265481899d9c6db46d654fef582d9f214</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/fedddeae402878841d2ac2cd9ae673888c521f58" target="_blank">Version update: 40e97400a6e04306180327b3ab3eceafc71268dc => 594e303265481899d9c6db46d654fef582d9f214</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/23044384438" target="_blank">2026-03-13 09:22:28</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16194" onclick="CopyToClipboard('tag16194');return false;" class="tag-decoration">release</div><div id="tag13887" onclick="CopyToClipboard('tag13887');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag20421" onclick="CopyToClipboard('tag20421');return false;" class="tag-decoration">release-4.5.5</div><div id="tag16632" onclick="CopyToClipboard('tag16632');return false;" class="tag-decoration">release-v4</div><div id="tag5421" onclick="CopyToClipboard('tag5421');return false;" class="tag-decoration">release-v4.5</div><div id="tag26033" onclick="CopyToClipboard('tag26033');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag27470" onclick="CopyToClipboard('tag27470');return false;" class="tag-decoration">testing</div><div id="tag3385" onclick="CopyToClipboard('tag3385');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag20473" onclick="CopyToClipboard('tag20473');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag12178" onclick="CopyToClipboard('tag12178');return false;" class="tag-decoration">testing-v4</div><div id="tag6002" onclick="CopyToClipboard('tag6002');return false;" class="tag-decoration">testing-v4.5</div><div id="tag8379" onclick="CopyToClipboard('tag8379');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
