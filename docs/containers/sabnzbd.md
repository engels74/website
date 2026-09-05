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
<tr><td><div id="tag5198" onclick="CopyToClipboard('tag5198');return false;" class="tag-decoration">nightly</div><div id="tag18672" onclick="CopyToClipboard('tag18672');return false;" class="tag-decoration">nightly-87a4e61</div><div id="tag14158" onclick="CopyToClipboard('tag14158');return false;" class="tag-decoration">nightly-d25d857fc4c6d1d7c7bf9fffb718074d50cda325</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/87a4e619ebeedf3ddecb8860e17b5c87d33932fb" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33969809265" target="_blank">2026-09-05 13:45:13</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26374" onclick="CopyToClipboard('tag26374');return false;" class="tag-decoration">release</div><div id="tag19493" onclick="CopyToClipboard('tag19493');return false;" class="tag-decoration">release-cafbc77</div><div id="tag31949" onclick="CopyToClipboard('tag31949');return false;" class="tag-decoration">release-5.1.2</div><div id="tag23089" onclick="CopyToClipboard('tag23089');return false;" class="tag-decoration">release-v5</div><div id="tag23874" onclick="CopyToClipboard('tag23874');return false;" class="tag-decoration">release-v5.1</div><div id="tag27335" onclick="CopyToClipboard('tag27335');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/cafbc777601259a03ceca50aa267c068661278eb" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33947192984" target="_blank">2026-09-05 05:24:16</a></td></tr>
<tr><td><div id="tag15047" onclick="CopyToClipboard('tag15047');return false;" class="tag-decoration">testing</div><div id="tag23976" onclick="CopyToClipboard('tag23976');return false;" class="tag-decoration">testing-79f97ba</div><div id="tag32123" onclick="CopyToClipboard('tag32123');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag16452" onclick="CopyToClipboard('tag16452');return false;" class="tag-decoration">testing-v5</div><div id="tag29932" onclick="CopyToClipboard('tag29932');return false;" class="tag-decoration">testing-v5.1</div><div id="tag10864" onclick="CopyToClipboard('tag10864');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/79f97ba12e4d6fed9cb82b78e2bbbc376d407d2b" target="_blank">Modified: packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33947116306" target="_blank">2026-09-05 05:24:20</a></td></tr>
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
