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
<tr><td><div id="tag14614" onclick="CopyToClipboard('tag14614');return false;" class="tag-decoration">nightly</div><div id="tag3570" onclick="CopyToClipboard('tag3570');return false;" class="tag-decoration">nightly-c864a2c</div><div id="tag26797" onclick="CopyToClipboard('tag26797');return false;" class="tag-decoration">nightly-98dc18388139ef9487e2b67479fefcef62a2d219</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/c864a2c621cd1a4fc8a76e2f0a69bf5959979e4d" target="_blank">Version update: 791650960b30394f36671b5b2477fb02f2b7ed4d => 98dc18388139ef9487e2b67479fefcef62a2d219</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25327367491" target="_blank">2026-05-04 15:19:16</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag26575" onclick="CopyToClipboard('tag26575');return false;" class="tag-decoration">release</div><div id="tag28840" onclick="CopyToClipboard('tag28840');return false;" class="tag-decoration">release-8d79706</div><div id="tag22810" onclick="CopyToClipboard('tag22810');return false;" class="tag-decoration">release-5.0.1</div><div id="tag17176" onclick="CopyToClipboard('tag17176');return false;" class="tag-decoration">release-v5</div><div id="tag25779" onclick="CopyToClipboard('tag25779');return false;" class="tag-decoration">release-v5.0</div><div id="tag23689" onclick="CopyToClipboard('tag23689');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8d7970682214e86f4df593db68c24b605a1a5718" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254172" target="_blank">2026-05-01 21:37:08</a></td></tr>
<tr><td><div id="tag13604" onclick="CopyToClipboard('tag13604');return false;" class="tag-decoration">testing</div><div id="tag9378" onclick="CopyToClipboard('tag9378');return false;" class="tag-decoration">testing-2b55556</div><div id="tag9144" onclick="CopyToClipboard('tag9144');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag7974" onclick="CopyToClipboard('tag7974');return false;" class="tag-decoration">testing-v5</div><div id="tag9168" onclick="CopyToClipboard('tag9168');return false;" class="tag-decoration">testing-v5.0</div><div id="tag31128" onclick="CopyToClipboard('tag31128');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b5555662f7d34c27829058643eff45c1b6eee87" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254956" target="_blank">2026-05-01 21:37:10</a></td></tr>
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
