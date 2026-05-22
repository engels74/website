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
<tr><td><div id="tag6530" onclick="CopyToClipboard('tag6530');return false;" class="tag-decoration">nightly</div><div id="tag16475" onclick="CopyToClipboard('tag16475');return false;" class="tag-decoration">nightly-ee76d6e</div><div id="tag7670" onclick="CopyToClipboard('tag7670');return false;" class="tag-decoration">nightly-820442bdbddae83497cd90a17e69b1216cef2916</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/ee76d6e350d1693a5b0405c916d49f7a4b410ac9" target="_blank">Modified: meta.json, packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26287574821" target="_blank">2026-05-22 12:24:04</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag10549" onclick="CopyToClipboard('tag10549');return false;" class="tag-decoration">release</div><div id="tag10553" onclick="CopyToClipboard('tag10553');return false;" class="tag-decoration">release-5151550</div><div id="tag21294" onclick="CopyToClipboard('tag21294');return false;" class="tag-decoration">release-5.0.3</div><div id="tag20812" onclick="CopyToClipboard('tag20812');return false;" class="tag-decoration">release-v5</div><div id="tag22973" onclick="CopyToClipboard('tag22973');return false;" class="tag-decoration">release-v5.0</div><div id="tag15564" onclick="CopyToClipboard('tag15564');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5151550479f178f84b7e3deeb61850d5f803323e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26192425184" target="_blank">2026-05-20 21:59:08</a></td></tr>
<tr><td><div id="tag13276" onclick="CopyToClipboard('tag13276');return false;" class="tag-decoration">testing</div><div id="tag21796" onclick="CopyToClipboard('tag21796');return false;" class="tag-decoration">testing-8806b84</div><div id="tag13803" onclick="CopyToClipboard('tag13803');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag12642" onclick="CopyToClipboard('tag12642');return false;" class="tag-decoration">testing-v5</div><div id="tag20272" onclick="CopyToClipboard('tag20272');return false;" class="tag-decoration">testing-v5.0</div><div id="tag11081" onclick="CopyToClipboard('tag11081');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8806b84f19af7e435040ffbdf575cca033b71bd1" target="_blank">Modified: meta.json, packages.txt</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26287572564" target="_blank">2026-05-22 12:24:01</a></td></tr>
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
