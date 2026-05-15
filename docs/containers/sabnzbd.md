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
<tr><td><div id="tag25233" onclick="CopyToClipboard('tag25233');return false;" class="tag-decoration">nightly</div><div id="tag13893" onclick="CopyToClipboard('tag13893');return false;" class="tag-decoration">nightly-b6008b8</div><div id="tag5724" onclick="CopyToClipboard('tag5724');return false;" class="tag-decoration">nightly-60f555117c78466704bcb82b22cc5027944e8139</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/b6008b87757315dad2a49fda4caba773ea001958" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932486590" target="_blank">2026-05-15 17:43:01</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag17776" onclick="CopyToClipboard('tag17776');return false;" class="tag-decoration">release</div><div id="tag27801" onclick="CopyToClipboard('tag27801');return false;" class="tag-decoration">release-4bec790</div><div id="tag19354" onclick="CopyToClipboard('tag19354');return false;" class="tag-decoration">release-5.0.3</div><div id="tag22326" onclick="CopyToClipboard('tag22326');return false;" class="tag-decoration">release-v5</div><div id="tag29558" onclick="CopyToClipboard('tag29558');return false;" class="tag-decoration">release-v5.0</div><div id="tag9969" onclick="CopyToClipboard('tag9969');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/4bec790507a8b73efeb2c4217246e129a9c357a4" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932485279" target="_blank">2026-05-15 17:42:59</a></td></tr>
<tr><td><div id="tag16424" onclick="CopyToClipboard('tag16424');return false;" class="tag-decoration">testing</div><div id="tag16565" onclick="CopyToClipboard('tag16565');return false;" class="tag-decoration">testing-89eb06e</div><div id="tag28811" onclick="CopyToClipboard('tag28811');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag14431" onclick="CopyToClipboard('tag14431');return false;" class="tag-decoration">testing-v5</div><div id="tag14211" onclick="CopyToClipboard('tag14211');return false;" class="tag-decoration">testing-v5.0</div><div id="tag25641" onclick="CopyToClipboard('tag25641');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/89eb06ea7ddb5c4fd27028fdbf0b1df485f7f8a8" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25932492370" target="_blank">2026-05-15 17:43:09</a></td></tr>
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
