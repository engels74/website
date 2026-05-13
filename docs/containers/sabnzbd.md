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
<tr><td><div id="tag4262" onclick="CopyToClipboard('tag4262');return false;" class="tag-decoration">nightly</div><div id="tag2585" onclick="CopyToClipboard('tag2585');return false;" class="tag-decoration">nightly-67a32a6</div><div id="tag3604" onclick="CopyToClipboard('tag3604');return false;" class="tag-decoration">nightly-b942e06297ab039a6ff848d5e479ec374ab907f2</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/67a32a67a5a3d1558ec9cee4ea89c2f3e333a642" target="_blank">Version update: 5598db0d9e5df3a94a6ebb0dd46261d4b1d96bea => b942e06297ab039a6ff848d5e479ec374ab907f2</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25809378179" target="_blank">2026-05-13 15:34:37</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag24120" onclick="CopyToClipboard('tag24120');return false;" class="tag-decoration">release</div><div id="tag30162" onclick="CopyToClipboard('tag30162');return false;" class="tag-decoration">release-649b812</div><div id="tag9453" onclick="CopyToClipboard('tag9453');return false;" class="tag-decoration">release-5.0.1</div><div id="tag13381" onclick="CopyToClipboard('tag13381');return false;" class="tag-decoration">release-v5</div><div id="tag18050" onclick="CopyToClipboard('tag18050');return false;" class="tag-decoration">release-v5.0</div><div id="tag14814" onclick="CopyToClipboard('tag14814');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/649b812ac39bc1438fd036c57634649a269e6095" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25720796668" target="_blank">2026-05-12 07:45:03</a></td></tr>
<tr><td><div id="tag31415" onclick="CopyToClipboard('tag31415');return false;" class="tag-decoration">testing</div><div id="tag21818" onclick="CopyToClipboard('tag21818');return false;" class="tag-decoration">testing-f1c91ab</div><div id="tag2940" onclick="CopyToClipboard('tag2940');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag1660" onclick="CopyToClipboard('tag1660');return false;" class="tag-decoration">testing-v5</div><div id="tag12908" onclick="CopyToClipboard('tag12908');return false;" class="tag-decoration">testing-v5.0</div><div id="tag2640" onclick="CopyToClipboard('tag2640');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/f1c91ab1227b24e3a2a1950ddcc065e4b7e1a1ef" target="_blank">Upstream or Packages update</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25720803851" target="_blank">2026-05-12 07:45:11</a></td></tr>
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
