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
<tr><td><div id="tag30385" onclick="CopyToClipboard('tag30385');return false;" class="tag-decoration">nightly</div><div id="tag974" onclick="CopyToClipboard('tag974');return false;" class="tag-decoration">nightly-64092df</div><div id="tag1602" onclick="CopyToClipboard('tag1602');return false;" class="tag-decoration">nightly-14e00b366ec9e110234d82b6425af96deb7bbf8d</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/64092df051a1f7c97bf5b6479d53aac5615c6b79" target="_blank">Version update: 449157e0fb9d8996d3b4378efee2503e7475cdb4 => 14e00b366ec9e110234d82b6425af96deb7bbf8d</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/23365797259" target="_blank">2026-03-20 22:53:38</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag17509" onclick="CopyToClipboard('tag17509');return false;" class="tag-decoration">release</div><div id="tag2027" onclick="CopyToClipboard('tag2027');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag25873" onclick="CopyToClipboard('tag25873');return false;" class="tag-decoration">release-4.5.5</div><div id="tag25789" onclick="CopyToClipboard('tag25789');return false;" class="tag-decoration">release-v4</div><div id="tag32452" onclick="CopyToClipboard('tag32452');return false;" class="tag-decoration">release-v4.5</div><div id="tag22084" onclick="CopyToClipboard('tag22084');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag22647" onclick="CopyToClipboard('tag22647');return false;" class="tag-decoration">testing</div><div id="tag28504" onclick="CopyToClipboard('tag28504');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag13253" onclick="CopyToClipboard('tag13253');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag6732" onclick="CopyToClipboard('tag6732');return false;" class="tag-decoration">testing-v4</div><div id="tag3986" onclick="CopyToClipboard('tag3986');return false;" class="tag-decoration">testing-v4.5</div><div id="tag30146" onclick="CopyToClipboard('tag30146');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
