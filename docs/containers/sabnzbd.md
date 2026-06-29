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
<tr><td><div id="tag22143" onclick="CopyToClipboard('tag22143');return false;" class="tag-decoration">nightly</div><div id="tag28707" onclick="CopyToClipboard('tag28707');return false;" class="tag-decoration">nightly-598a2a6</div><div id="tag19004" onclick="CopyToClipboard('tag19004');return false;" class="tag-decoration">nightly-dbe7cb336d9f09ba4e782fb88854a7cfa8a59563</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/598a2a6471d1bc5d2db1f9188657364486456ff4" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28391311289" target="_blank">2026-06-29 17:40:51</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag14570" onclick="CopyToClipboard('tag14570');return false;" class="tag-decoration">release</div><div id="tag4369" onclick="CopyToClipboard('tag4369');return false;" class="tag-decoration">release-7dcae8e</div><div id="tag11944" onclick="CopyToClipboard('tag11944');return false;" class="tag-decoration">release-5.0.4</div><div id="tag24076" onclick="CopyToClipboard('tag24076');return false;" class="tag-decoration">release-v5</div><div id="tag12695" onclick="CopyToClipboard('tag12695');return false;" class="tag-decoration">release-v5.0</div><div id="tag7802" onclick="CopyToClipboard('tag7802');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7dcae8eaa21d3fc246cf22dcb5abe05713efd24a" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27987238337" target="_blank">2026-06-22 22:06:19</a></td></tr>
<tr><td><div id="tag18268" onclick="CopyToClipboard('tag18268');return false;" class="tag-decoration">testing</div><div id="tag3540" onclick="CopyToClipboard('tag3540');return false;" class="tag-decoration">testing-e30a4d5</div><div id="tag14945" onclick="CopyToClipboard('tag14945');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag7470" onclick="CopyToClipboard('tag7470');return false;" class="tag-decoration">testing-v5</div><div id="tag9808" onclick="CopyToClipboard('tag9808');return false;" class="tag-decoration">testing-v5.0</div><div id="tag17880" onclick="CopyToClipboard('tag17880');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/e30a4d5b461554eae493fe1d036bfa8c49286ce1" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28391307438" target="_blank">2026-06-29 17:40:47</a></td></tr>
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
