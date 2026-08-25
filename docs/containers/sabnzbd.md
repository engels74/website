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
<tr><td><div id="tag22008" onclick="CopyToClipboard('tag22008');return false;" class="tag-decoration">nightly</div><div id="tag24873" onclick="CopyToClipboard('tag24873');return false;" class="tag-decoration">nightly-07a74a2</div><div id="tag23791" onclick="CopyToClipboard('tag23791');return false;" class="tag-decoration">nightly-f498147189f325393c5b762279b8cf708aa37e56</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/07a74a2f676ca7cd05828130c1b266d7be8d844d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32842740996" target="_blank">2026-08-25 11:31:14</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag21769" onclick="CopyToClipboard('tag21769');return false;" class="tag-decoration">release</div><div id="tag32661" onclick="CopyToClipboard('tag32661');return false;" class="tag-decoration">release-9ea1119</div><div id="tag17578" onclick="CopyToClipboard('tag17578');return false;" class="tag-decoration">release-5.1.2</div><div id="tag750" onclick="CopyToClipboard('tag750');return false;" class="tag-decoration">release-v5</div><div id="tag8102" onclick="CopyToClipboard('tag8102');return false;" class="tag-decoration">release-v5.1</div><div id="tag19426" onclick="CopyToClipboard('tag19426');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/9ea11196defff1c60c1f20baca9f92c7e73d9317" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32861952518" target="_blank">2026-08-25 14:49:40</a></td></tr>
<tr><td><div id="tag31336" onclick="CopyToClipboard('tag31336');return false;" class="tag-decoration">testing</div><div id="tag25109" onclick="CopyToClipboard('tag25109');return false;" class="tag-decoration">testing-e417274</div><div id="tag2663" onclick="CopyToClipboard('tag2663');return false;" class="tag-decoration">testing-5.1.1</div><div id="tag31976" onclick="CopyToClipboard('tag31976');return false;" class="tag-decoration">testing-v5</div><div id="tag12277" onclick="CopyToClipboard('tag12277');return false;" class="tag-decoration">testing-v5.1</div><div id="tag979" onclick="CopyToClipboard('tag979');return false;" class="tag-decoration">testing-v5.1.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e417274da1817bfeeeadbb99d597f90b9d06a636" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32381393649" target="_blank">2026-08-20 14:38:53</a></td></tr>
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
