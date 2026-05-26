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
<tr><td><div id="tag19781" onclick="CopyToClipboard('tag19781');return false;" class="tag-decoration">nightly</div><div id="tag13580" onclick="CopyToClipboard('tag13580');return false;" class="tag-decoration">nightly-51b399a</div><div id="tag27532" onclick="CopyToClipboard('tag27532');return false;" class="tag-decoration">nightly-b0c31c7e10769c7d84b1db8ec62b9e8373e63e46</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/51b399a45e73e6e93bfcd4543ae077f7c6b76b4c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26439792071" target="_blank">2026-05-26 07:55:29</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag17601" onclick="CopyToClipboard('tag17601');return false;" class="tag-decoration">release</div><div id="tag8422" onclick="CopyToClipboard('tag8422');return false;" class="tag-decoration">release-3577c35</div><div id="tag22759" onclick="CopyToClipboard('tag22759');return false;" class="tag-decoration">release-5.0.3</div><div id="tag13107" onclick="CopyToClipboard('tag13107');return false;" class="tag-decoration">release-v5</div><div id="tag21528" onclick="CopyToClipboard('tag21528');return false;" class="tag-decoration">release-v5.0</div><div id="tag4409" onclick="CopyToClipboard('tag4409');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3577c35caa29187d2d76ee36cad710fba3e90548" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26363856550" target="_blank">2026-05-24 14:26:18</a></td></tr>
<tr><td><div id="tag7077" onclick="CopyToClipboard('tag7077');return false;" class="tag-decoration">testing</div><div id="tag8922" onclick="CopyToClipboard('tag8922');return false;" class="tag-decoration">testing-9e0e5ab</div><div id="tag9941" onclick="CopyToClipboard('tag9941');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag3074" onclick="CopyToClipboard('tag3074');return false;" class="tag-decoration">testing-v5</div><div id="tag18594" onclick="CopyToClipboard('tag18594');return false;" class="tag-decoration">testing-v5.0</div><div id="tag21008" onclick="CopyToClipboard('tag21008');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/9e0e5abe127f87f579be820d0353c0ce0c1f4762" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26363856297" target="_blank">2026-05-24 14:26:17</a></td></tr>
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
