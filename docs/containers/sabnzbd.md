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
<tr><td><div id="tag26115" onclick="CopyToClipboard('tag26115');return false;" class="tag-decoration">nightly</div><div id="tag29036" onclick="CopyToClipboard('tag29036');return false;" class="tag-decoration">nightly-e5dfaa5</div><div id="tag13780" onclick="CopyToClipboard('tag13780');return false;" class="tag-decoration">nightly-4a999a19081b76cff813b1c0e13bfea2234f314a</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e5dfaa592b6fb217aa1b362110d6db51cfc39123" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33587837574" target="_blank">2026-09-02 03:39:02</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29794" onclick="CopyToClipboard('tag29794');return false;" class="tag-decoration">release</div><div id="tag29964" onclick="CopyToClipboard('tag29964');return false;" class="tag-decoration">release-62027b7</div><div id="tag8194" onclick="CopyToClipboard('tag8194');return false;" class="tag-decoration">release-5.1.2</div><div id="tag24632" onclick="CopyToClipboard('tag24632');return false;" class="tag-decoration">release-v5</div><div id="tag2124" onclick="CopyToClipboard('tag2124');return false;" class="tag-decoration">release-v5.1</div><div id="tag28846" onclick="CopyToClipboard('tag28846');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/62027b707cffa4343cee0adf56ba3bf7d8748da9" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33587832465" target="_blank">2026-09-02 03:38:57</a></td></tr>
<tr><td><div id="tag27639" onclick="CopyToClipboard('tag27639');return false;" class="tag-decoration">testing</div><div id="tag2680" onclick="CopyToClipboard('tag2680');return false;" class="tag-decoration">testing-d904f6b</div><div id="tag28284" onclick="CopyToClipboard('tag28284');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag22989" onclick="CopyToClipboard('tag22989');return false;" class="tag-decoration">testing-v5</div><div id="tag24951" onclick="CopyToClipboard('tag24951');return false;" class="tag-decoration">testing-v5.1</div><div id="tag8320" onclick="CopyToClipboard('tag8320');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/d904f6b3e1dddcb5c0abc1ba3f85f4f7e242a439" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33587839008" target="_blank">2026-09-02 03:39:04</a></td></tr>
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
