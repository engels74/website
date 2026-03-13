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
<tr><td><div id="tag14022" onclick="CopyToClipboard('tag14022');return false;" class="tag-decoration">nightly</div><div id="tag8718" onclick="CopyToClipboard('tag8718');return false;" class="tag-decoration">nightly-d01f2f6</div><div id="tag11771" onclick="CopyToClipboard('tag11771');return false;" class="tag-decoration">nightly-6cc19033f82d3bfaee52a071f341267caebff5cb</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d01f2f66cd1f6bf03afb9e8feb2df702074c814b" target="_blank">Version update: 594e303265481899d9c6db46d654fef582d9f214 => 6cc19033f82d3bfaee52a071f341267caebff5cb</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/23047663195" target="_blank">2026-03-13 10:55:25</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag166" onclick="CopyToClipboard('tag166');return false;" class="tag-decoration">release</div><div id="tag27988" onclick="CopyToClipboard('tag27988');return false;" class="tag-decoration">release-33f5e7f</div><div id="tag22862" onclick="CopyToClipboard('tag22862');return false;" class="tag-decoration">release-4.5.5</div><div id="tag17976" onclick="CopyToClipboard('tag17976');return false;" class="tag-decoration">release-v4</div><div id="tag30429" onclick="CopyToClipboard('tag30429');return false;" class="tag-decoration">release-v4.5</div><div id="tag22103" onclick="CopyToClipboard('tag22103');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/33f5e7fdb3b3bca2cd7dbbb9774a5a7f05b0882d" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724225" target="_blank">2026-02-25 21:28:58</a></td></tr>
<tr><td><div id="tag16330" onclick="CopyToClipboard('tag16330');return false;" class="tag-decoration">testing</div><div id="tag9426" onclick="CopyToClipboard('tag9426');return false;" class="tag-decoration">testing-ea619d5</div><div id="tag21727" onclick="CopyToClipboard('tag21727');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag9957" onclick="CopyToClipboard('tag9957');return false;" class="tag-decoration">testing-v4</div><div id="tag21405" onclick="CopyToClipboard('tag21405');return false;" class="tag-decoration">testing-v4.5</div><div id="tag20673" onclick="CopyToClipboard('tag20673');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ea619d52d293907d9b72038e1dff39f72d870f2e" target="_blank">Upstream update: alpinevpn-6d5cbf5 => alpinevpn-167fa4e</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22416724984" target="_blank">2026-02-25 21:28:59</a></td></tr>
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
