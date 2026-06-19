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
<tr><td><div id="tag18349" onclick="CopyToClipboard('tag18349');return false;" class="tag-decoration">nightly</div><div id="tag17459" onclick="CopyToClipboard('tag17459');return false;" class="tag-decoration">nightly-7934c07</div><div id="tag13657" onclick="CopyToClipboard('tag13657');return false;" class="tag-decoration">nightly-f0d3e6b8b9f1454bce19f7027dd16878ba1b575c</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/7934c0740b30233cb8c915bc9e4ff21082ccde55" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27824880717" target="_blank">2026-06-19 12:10:23</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20202" onclick="CopyToClipboard('tag20202');return false;" class="tag-decoration">release</div><div id="tag32646" onclick="CopyToClipboard('tag32646');return false;" class="tag-decoration">release-746e018</div><div id="tag7443" onclick="CopyToClipboard('tag7443');return false;" class="tag-decoration">release-5.0.4</div><div id="tag5564" onclick="CopyToClipboard('tag5564');return false;" class="tag-decoration">release-v5</div><div id="tag3236" onclick="CopyToClipboard('tag3236');return false;" class="tag-decoration">release-v5.0</div><div id="tag9520" onclick="CopyToClipboard('tag9520');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/746e018cd50910dae73acbd4ab2ae90183233d6c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354913378" target="_blank">2026-06-11 14:40:57</a></td></tr>
<tr><td><div id="tag27420" onclick="CopyToClipboard('tag27420');return false;" class="tag-decoration">testing</div><div id="tag4240" onclick="CopyToClipboard('tag4240');return false;" class="tag-decoration">testing-1b1942e</div><div id="tag17719" onclick="CopyToClipboard('tag17719');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag432" onclick="CopyToClipboard('tag432');return false;" class="tag-decoration">testing-v5</div><div id="tag31214" onclick="CopyToClipboard('tag31214');return false;" class="tag-decoration">testing-v5.0</div><div id="tag2524" onclick="CopyToClipboard('tag2524');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b1942e349033b72b39f15958dc0694493b2d37d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354916499" target="_blank">2026-06-11 14:40:59</a></td></tr>
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
