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
<tr><td><div id="tag27228" onclick="CopyToClipboard('tag27228');return false;" class="tag-decoration">nightly</div><div id="tag9811" onclick="CopyToClipboard('tag9811');return false;" class="tag-decoration">nightly-d8e6ab4</div><div id="tag5235" onclick="CopyToClipboard('tag5235');return false;" class="tag-decoration">nightly-d7ca91e3955f7c87dcd662c33469740fc9791206</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/d8e6ab47d6e1ad61ea154db7a614de15eff604e8" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25972686346" target="_blank">2026-05-16 20:54:10</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag18126" onclick="CopyToClipboard('tag18126');return false;" class="tag-decoration">release</div><div id="tag30503" onclick="CopyToClipboard('tag30503');return false;" class="tag-decoration">release-6b59852</div><div id="tag17117" onclick="CopyToClipboard('tag17117');return false;" class="tag-decoration">release-5.0.3</div><div id="tag4199" onclick="CopyToClipboard('tag4199');return false;" class="tag-decoration">release-v5</div><div id="tag10145" onclick="CopyToClipboard('tag10145');return false;" class="tag-decoration">release-v5.0</div><div id="tag27607" onclick="CopyToClipboard('tag27607');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/6b59852fcbb08ef8cbf9b183bb25ff7450e5bbd7" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25965096351" target="_blank">2026-05-16 15:00:04</a></td></tr>
<tr><td><div id="tag926" onclick="CopyToClipboard('tag926');return false;" class="tag-decoration">testing</div><div id="tag23321" onclick="CopyToClipboard('tag23321');return false;" class="tag-decoration">testing-35d13c7</div><div id="tag26622" onclick="CopyToClipboard('tag26622');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag3005" onclick="CopyToClipboard('tag3005');return false;" class="tag-decoration">testing-v5</div><div id="tag26955" onclick="CopyToClipboard('tag26955');return false;" class="tag-decoration">testing-v5.0</div><div id="tag32502" onclick="CopyToClipboard('tag32502');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/35d13c73bbf2a9df84b9f418f06997c57fd101c3" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25965096696" target="_blank">2026-05-16 15:00:05</a></td></tr>
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
