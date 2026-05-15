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
<tr><td><div id="tag31521" onclick="CopyToClipboard('tag31521');return false;" class="tag-decoration">nightly</div><div id="tag3441" onclick="CopyToClipboard('tag3441');return false;" class="tag-decoration">nightly-7dfcc7f</div><div id="tag91" onclick="CopyToClipboard('tag91');return false;" class="tag-decoration">nightly-8069361faaf6f00d384af990634538c28bcec619</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7dfcc7f4573d9a75c6ad49790cb03742ee64afbb" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25937892059" target="_blank">2026-05-15 19:43:57</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag28467" onclick="CopyToClipboard('tag28467');return false;" class="tag-decoration">release</div><div id="tag12885" onclick="CopyToClipboard('tag12885');return false;" class="tag-decoration">release-4bec790</div><div id="tag24885" onclick="CopyToClipboard('tag24885');return false;" class="tag-decoration">release-5.0.3</div><div id="tag8193" onclick="CopyToClipboard('tag8193');return false;" class="tag-decoration">release-v5</div><div id="tag2223" onclick="CopyToClipboard('tag2223');return false;" class="tag-decoration">release-v5.0</div><div id="tag9209" onclick="CopyToClipboard('tag9209');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4bec790507a8b73efeb2c4217246e129a9c357a4" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932485279" target="_blank">2026-05-15 17:42:59</a></td></tr>
<tr><td><div id="tag17977" onclick="CopyToClipboard('tag17977');return false;" class="tag-decoration">testing</div><div id="tag10528" onclick="CopyToClipboard('tag10528');return false;" class="tag-decoration">testing-89eb06e</div><div id="tag25541" onclick="CopyToClipboard('tag25541');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag27380" onclick="CopyToClipboard('tag27380');return false;" class="tag-decoration">testing-v5</div><div id="tag27946" onclick="CopyToClipboard('tag27946');return false;" class="tag-decoration">testing-v5.0</div><div id="tag32626" onclick="CopyToClipboard('tag32626');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/89eb06ea7ddb5c4fd27028fdbf0b1df485f7f8a8" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932492370" target="_blank">2026-05-15 17:43:09</a></td></tr>
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
