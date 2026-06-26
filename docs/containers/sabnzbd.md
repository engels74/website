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
<tr><td><div id="tag3182" onclick="CopyToClipboard('tag3182');return false;" class="tag-decoration">nightly</div><div id="tag6364" onclick="CopyToClipboard('tag6364');return false;" class="tag-decoration">nightly-a8d3e3a</div><div id="tag2301" onclick="CopyToClipboard('tag2301');return false;" class="tag-decoration">nightly-a55251f698bb41cc1e4146344121646ce9b88ad9</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/a8d3e3a953b4ca0ed3496a3af7f93f292af27dca" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28247722870" target="_blank">2026-06-26 15:24:57</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag1983" onclick="CopyToClipboard('tag1983');return false;" class="tag-decoration">release</div><div id="tag16053" onclick="CopyToClipboard('tag16053');return false;" class="tag-decoration">release-7dcae8e</div><div id="tag12428" onclick="CopyToClipboard('tag12428');return false;" class="tag-decoration">release-5.0.4</div><div id="tag1123" onclick="CopyToClipboard('tag1123');return false;" class="tag-decoration">release-v5</div><div id="tag6395" onclick="CopyToClipboard('tag6395');return false;" class="tag-decoration">release-v5.0</div><div id="tag9837" onclick="CopyToClipboard('tag9837');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7dcae8eaa21d3fc246cf22dcb5abe05713efd24a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27987238337" target="_blank">2026-06-22 22:06:19</a></td></tr>
<tr><td><div id="tag28527" onclick="CopyToClipboard('tag28527');return false;" class="tag-decoration">testing</div><div id="tag10645" onclick="CopyToClipboard('tag10645');return false;" class="tag-decoration">testing-0afca37</div><div id="tag22083" onclick="CopyToClipboard('tag22083');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag26541" onclick="CopyToClipboard('tag26541');return false;" class="tag-decoration">testing-v5</div><div id="tag27443" onclick="CopyToClipboard('tag27443');return false;" class="tag-decoration">testing-v5.0</div><div id="tag28459" onclick="CopyToClipboard('tag28459');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/0afca379eb53eabd2b0061d2c89351357c56d806" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27987238526" target="_blank">2026-06-22 22:06:20</a></td></tr>
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
