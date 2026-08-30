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
<tr><td><div id="tag31660" onclick="CopyToClipboard('tag31660');return false;" class="tag-decoration">nightly</div><div id="tag16675" onclick="CopyToClipboard('tag16675');return false;" class="tag-decoration">nightly-c948614</div><div id="tag32328" onclick="CopyToClipboard('tag32328');return false;" class="tag-decoration">nightly-614b3faca60145e3f5387f50b845ad5876133497</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c9486149cf4afc2d3fd1a3bad733a6645cd74336" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33330091395" target="_blank">2026-08-30 19:09:44</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26903" onclick="CopyToClipboard('tag26903');return false;" class="tag-decoration">release</div><div id="tag7369" onclick="CopyToClipboard('tag7369');return false;" class="tag-decoration">release-3699da3</div><div id="tag10163" onclick="CopyToClipboard('tag10163');return false;" class="tag-decoration">release-5.1.2</div><div id="tag232" onclick="CopyToClipboard('tag232');return false;" class="tag-decoration">release-v5</div><div id="tag5714" onclick="CopyToClipboard('tag5714');return false;" class="tag-decoration">release-v5.1</div><div id="tag19609" onclick="CopyToClipboard('tag19609');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3699da399bd995c96fef64e914b2ef5e02caa282" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919084624" target="_blank">2026-08-26 01:28:09</a></td></tr>
<tr><td><div id="tag25969" onclick="CopyToClipboard('tag25969');return false;" class="tag-decoration">testing</div><div id="tag24289" onclick="CopyToClipboard('tag24289');return false;" class="tag-decoration">testing-00935f0</div><div id="tag14083" onclick="CopyToClipboard('tag14083');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag5296" onclick="CopyToClipboard('tag5296');return false;" class="tag-decoration">testing-v5</div><div id="tag2455" onclick="CopyToClipboard('tag2455');return false;" class="tag-decoration">testing-v5.1</div><div id="tag20879" onclick="CopyToClipboard('tag20879');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/00935f0d6744379ad94969d7f14fa72e46fe68c7" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32919082616" target="_blank">2026-08-26 01:28:07</a></td></tr>
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
