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
<tr><td><div id="tag24472" onclick="CopyToClipboard('tag24472');return false;" class="tag-decoration">nightly</div><div id="tag18369" onclick="CopyToClipboard('tag18369');return false;" class="tag-decoration">nightly-47fc5e2</div><div id="tag22743" onclick="CopyToClipboard('tag22743');return false;" class="tag-decoration">nightly-cc61dc974b383e5bce04746274407448b6d0443e</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/47fc5e273497c433b8de9bfe8b22982b9513c589" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26680261829" target="_blank">2026-05-30 09:21:23</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag32676" onclick="CopyToClipboard('tag32676');return false;" class="tag-decoration">release</div><div id="tag15875" onclick="CopyToClipboard('tag15875');return false;" class="tag-decoration">release-2d120d6</div><div id="tag656" onclick="CopyToClipboard('tag656');return false;" class="tag-decoration">release-5.0.3</div><div id="tag12281" onclick="CopyToClipboard('tag12281');return false;" class="tag-decoration">release-v5</div><div id="tag10771" onclick="CopyToClipboard('tag10771');return false;" class="tag-decoration">release-v5.0</div><div id="tag4931" onclick="CopyToClipboard('tag4931');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2d120d6b41fd93f6be7ece5400744e5551bc94f4" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26680261017" target="_blank">2026-05-30 09:21:21</a></td></tr>
<tr><td><div id="tag23347" onclick="CopyToClipboard('tag23347');return false;" class="tag-decoration">testing</div><div id="tag30020" onclick="CopyToClipboard('tag30020');return false;" class="tag-decoration">testing-35e86b1</div><div id="tag19798" onclick="CopyToClipboard('tag19798');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag4949" onclick="CopyToClipboard('tag4949');return false;" class="tag-decoration">testing-v5</div><div id="tag6249" onclick="CopyToClipboard('tag6249');return false;" class="tag-decoration">testing-v5.0</div><div id="tag20346" onclick="CopyToClipboard('tag20346');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/35e86b1ac46e08f79c1335f266179e63eb9f2be5" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26680261806" target="_blank">2026-05-30 09:21:23</a></td></tr>
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
