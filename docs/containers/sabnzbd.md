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
<tr><td><div id="tag13540" onclick="CopyToClipboard('tag13540');return false;" class="tag-decoration">nightly</div><div id="tag5775" onclick="CopyToClipboard('tag5775');return false;" class="tag-decoration">nightly-e6a2381</div><div id="tag19795" onclick="CopyToClipboard('tag19795');return false;" class="tag-decoration">nightly-25d20f0f08ce2078402faf0e7b281db9ceb04643</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e6a23818c1b6a94ff6f548dffc0f5c55b40fad39" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26343379440" target="_blank">2026-05-23 20:57:34</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20532" onclick="CopyToClipboard('tag20532');return false;" class="tag-decoration">release</div><div id="tag3214" onclick="CopyToClipboard('tag3214');return false;" class="tag-decoration">release-70d8e60</div><div id="tag27999" onclick="CopyToClipboard('tag27999');return false;" class="tag-decoration">release-5.0.3</div><div id="tag1634" onclick="CopyToClipboard('tag1634');return false;" class="tag-decoration">release-v5</div><div id="tag25689" onclick="CopyToClipboard('tag25689');return false;" class="tag-decoration">release-v5.0</div><div id="tag14549" onclick="CopyToClipboard('tag14549');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/70d8e606c26349a1a1d3680daa07fb14e8908e3a" target="_blank">Modified: meta.json, packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26287574256" target="_blank">2026-05-22 12:24:03</a></td></tr>
<tr><td><div id="tag10482" onclick="CopyToClipboard('tag10482');return false;" class="tag-decoration">testing</div><div id="tag28183" onclick="CopyToClipboard('tag28183');return false;" class="tag-decoration">testing-aa16204</div><div id="tag11672" onclick="CopyToClipboard('tag11672');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag31263" onclick="CopyToClipboard('tag31263');return false;" class="tag-decoration">testing-v5</div><div id="tag3210" onclick="CopyToClipboard('tag3210');return false;" class="tag-decoration">testing-v5.0</div><div id="tag19268" onclick="CopyToClipboard('tag19268');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aa16204d41da4854c3414a4c58e6c8e59abd15a0" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26343379597" target="_blank">2026-05-23 20:57:35</a></td></tr>
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
