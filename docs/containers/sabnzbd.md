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
<tr><td><div id="tag1163" onclick="CopyToClipboard('tag1163');return false;" class="tag-decoration">nightly</div><div id="tag14005" onclick="CopyToClipboard('tag14005');return false;" class="tag-decoration">nightly-7efa26a</div><div id="tag5739" onclick="CopyToClipboard('tag5739');return false;" class="tag-decoration">nightly-e3c8d79dae855079d2a279cb54b7be74b8709dda</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7efa26a442c9ac878ff1b721c3010e046476f0dc" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25965095941" target="_blank">2026-05-16 15:00:03</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag1364" onclick="CopyToClipboard('tag1364');return false;" class="tag-decoration">release</div><div id="tag6025" onclick="CopyToClipboard('tag6025');return false;" class="tag-decoration">release-6b59852</div><div id="tag3358" onclick="CopyToClipboard('tag3358');return false;" class="tag-decoration">release-5.0.3</div><div id="tag19122" onclick="CopyToClipboard('tag19122');return false;" class="tag-decoration">release-v5</div><div id="tag13386" onclick="CopyToClipboard('tag13386');return false;" class="tag-decoration">release-v5.0</div><div id="tag19295" onclick="CopyToClipboard('tag19295');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/6b59852fcbb08ef8cbf9b183bb25ff7450e5bbd7" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25965096351" target="_blank">2026-05-16 15:00:04</a></td></tr>
<tr><td><div id="tag11581" onclick="CopyToClipboard('tag11581');return false;" class="tag-decoration">testing</div><div id="tag27876" onclick="CopyToClipboard('tag27876');return false;" class="tag-decoration">testing-35d13c7</div><div id="tag13743" onclick="CopyToClipboard('tag13743');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag5935" onclick="CopyToClipboard('tag5935');return false;" class="tag-decoration">testing-v5</div><div id="tag5925" onclick="CopyToClipboard('tag5925');return false;" class="tag-decoration">testing-v5.0</div><div id="tag25804" onclick="CopyToClipboard('tag25804');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/35d13c73bbf2a9df84b9f418f06997c57fd101c3" target="_blank">Version, Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25965096696" target="_blank">2026-05-16 15:00:05</a></td></tr>
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
