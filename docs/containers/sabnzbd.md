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
<tr><td><div id="tag2358" onclick="CopyToClipboard('tag2358');return false;" class="tag-decoration">nightly</div><div id="tag29312" onclick="CopyToClipboard('tag29312');return false;" class="tag-decoration">nightly-e5fe7a9</div><div id="tag3367" onclick="CopyToClipboard('tag3367');return false;" class="tag-decoration">nightly-d25d857fc4c6d1d7c7bf9fffb718074d50cda325</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e5fe7a98d42317b3986c509b76492389142b67fa" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33947114437" target="_blank">2026-09-05 05:24:17</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag22625" onclick="CopyToClipboard('tag22625');return false;" class="tag-decoration">release</div><div id="tag7402" onclick="CopyToClipboard('tag7402');return false;" class="tag-decoration">release-cafbc77</div><div id="tag28862" onclick="CopyToClipboard('tag28862');return false;" class="tag-decoration">release-5.1.2</div><div id="tag363" onclick="CopyToClipboard('tag363');return false;" class="tag-decoration">release-v5</div><div id="tag21029" onclick="CopyToClipboard('tag21029');return false;" class="tag-decoration">release-v5.1</div><div id="tag6" onclick="CopyToClipboard('tag6');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/cafbc777601259a03ceca50aa267c068661278eb" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33947192984" target="_blank">2026-09-05 05:24:16</a></td></tr>
<tr><td><div id="tag27481" onclick="CopyToClipboard('tag27481');return false;" class="tag-decoration">testing</div><div id="tag9274" onclick="CopyToClipboard('tag9274');return false;" class="tag-decoration">testing-79f97ba</div><div id="tag20282" onclick="CopyToClipboard('tag20282');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag21344" onclick="CopyToClipboard('tag21344');return false;" class="tag-decoration">testing-v5</div><div id="tag4689" onclick="CopyToClipboard('tag4689');return false;" class="tag-decoration">testing-v5.1</div><div id="tag4151" onclick="CopyToClipboard('tag4151');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/79f97ba12e4d6fed9cb82b78e2bbbc376d407d2b" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33947116306" target="_blank">2026-09-05 05:24:20</a></td></tr>
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
