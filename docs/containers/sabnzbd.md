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
<tr><td><div id="tag4542" onclick="CopyToClipboard('tag4542');return false;" class="tag-decoration">nightly</div><div id="tag26349" onclick="CopyToClipboard('tag26349');return false;" class="tag-decoration">nightly-3273486</div><div id="tag7828" onclick="CopyToClipboard('tag7828');return false;" class="tag-decoration">nightly-3ab1782dc227cb7125d6ef538ace57d79033a39f</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/3273486ed5245093df882a4a4fc2cd37ae326a41" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29950913463" target="_blank">2026-07-22 19:25:30</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag17517" onclick="CopyToClipboard('tag17517');return false;" class="tag-decoration">release</div><div id="tag3806" onclick="CopyToClipboard('tag3806');return false;" class="tag-decoration">release-f2ff217</div><div id="tag26704" onclick="CopyToClipboard('tag26704');return false;" class="tag-decoration">release-5.0.4</div><div id="tag8761" onclick="CopyToClipboard('tag8761');return false;" class="tag-decoration">release-v5</div><div id="tag20170" onclick="CopyToClipboard('tag20170');return false;" class="tag-decoration">release-v5.0</div><div id="tag28561" onclick="CopyToClipboard('tag28561');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f2ff2170345d48b8af92799eccf20db6fd076ad4" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29691923095" target="_blank">2026-07-19 14:59:28</a></td></tr>
<tr><td><div id="tag13855" onclick="CopyToClipboard('tag13855');return false;" class="tag-decoration">testing</div><div id="tag16917" onclick="CopyToClipboard('tag16917');return false;" class="tag-decoration">testing-d8539b7</div><div id="tag24672" onclick="CopyToClipboard('tag24672');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag2495" onclick="CopyToClipboard('tag2495');return false;" class="tag-decoration">testing-v5</div><div id="tag17713" onclick="CopyToClipboard('tag17713');return false;" class="tag-decoration">testing-v5.0</div><div id="tag7215" onclick="CopyToClipboard('tag7215');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/d8539b793bcec0dc1d48546ec83a0627445bbf8e" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29691921612" target="_blank">2026-07-19 14:59:25</a></td></tr>
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
