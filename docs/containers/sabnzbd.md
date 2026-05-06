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
<tr><td><div id="tag23169" onclick="CopyToClipboard('tag23169');return false;" class="tag-decoration">nightly</div><div id="tag20967" onclick="CopyToClipboard('tag20967');return false;" class="tag-decoration">nightly-077700e</div><div id="tag23146" onclick="CopyToClipboard('tag23146');return false;" class="tag-decoration">nightly-95f3b9fcc1cf3e11ff210c71b94f27b0daff075d</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/077700eddeee69857356d8294f478e28f281b149" target="_blank">Version update: ae170c68791945c73a28c56907afd52e2204795d => 95f3b9fcc1cf3e11ff210c71b94f27b0daff075d</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25455036923" target="_blank">2026-05-06 18:58:15</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag20981" onclick="CopyToClipboard('tag20981');return false;" class="tag-decoration">release</div><div id="tag15757" onclick="CopyToClipboard('tag15757');return false;" class="tag-decoration">release-8d79706</div><div id="tag24834" onclick="CopyToClipboard('tag24834');return false;" class="tag-decoration">release-5.0.1</div><div id="tag29918" onclick="CopyToClipboard('tag29918');return false;" class="tag-decoration">release-v5</div><div id="tag11908" onclick="CopyToClipboard('tag11908');return false;" class="tag-decoration">release-v5.0</div><div id="tag10049" onclick="CopyToClipboard('tag10049');return false;" class="tag-decoration">release-v5.0.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8d7970682214e86f4df593db68c24b605a1a5718" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254172" target="_blank">2026-05-01 21:37:08</a></td></tr>
<tr><td><div id="tag2217" onclick="CopyToClipboard('tag2217');return false;" class="tag-decoration">testing</div><div id="tag6974" onclick="CopyToClipboard('tag6974');return false;" class="tag-decoration">testing-2b55556</div><div id="tag9645" onclick="CopyToClipboard('tag9645');return false;" class="tag-decoration">testing-5.0.1</div><div id="tag14861" onclick="CopyToClipboard('tag14861');return false;" class="tag-decoration">testing-v5</div><div id="tag3899" onclick="CopyToClipboard('tag3899');return false;" class="tag-decoration">testing-v5.0</div><div id="tag11622" onclick="CopyToClipboard('tag11622');return false;" class="tag-decoration">testing-v5.0.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/2b5555662f7d34c27829058643eff45c1b6eee87" target="_blank">Version update: 5.0.0 => 5.0.1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/25234254956" target="_blank">2026-05-01 21:37:10</a></td></tr>
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
