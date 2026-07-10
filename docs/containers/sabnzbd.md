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
<tr><td><div id="tag8126" onclick="CopyToClipboard('tag8126');return false;" class="tag-decoration">nightly</div><div id="tag30142" onclick="CopyToClipboard('tag30142');return false;" class="tag-decoration">nightly-311f974</div><div id="tag8855" onclick="CopyToClipboard('tag8855');return false;" class="tag-decoration">nightly-bf02e9da44316388c5b072f73c1b19bc1a55a13b</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/311f974e129fec0a1ba4ce40fe82ad5fbd690c34" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/29100367961" target="_blank">2026-07-10 14:34:55</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag12269" onclick="CopyToClipboard('tag12269');return false;" class="tag-decoration">release</div><div id="tag24027" onclick="CopyToClipboard('tag24027');return false;" class="tag-decoration">release-aa1692b</div><div id="tag16922" onclick="CopyToClipboard('tag16922');return false;" class="tag-decoration">release-5.0.4</div><div id="tag21416" onclick="CopyToClipboard('tag21416');return false;" class="tag-decoration">release-v5</div><div id="tag27022" onclick="CopyToClipboard('tag27022');return false;" class="tag-decoration">release-v5.0</div><div id="tag3104" onclick="CopyToClipboard('tag3104');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/aa1692b699b5339ee61eccad93ca9f3459641ddd" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979413673" target="_blank">2026-07-08 22:13:28</a></td></tr>
<tr><td><div id="tag24794" onclick="CopyToClipboard('tag24794');return false;" class="tag-decoration">testing</div><div id="tag30735" onclick="CopyToClipboard('tag30735');return false;" class="tag-decoration">testing-5fd6272</div><div id="tag23171" onclick="CopyToClipboard('tag23171');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag31633" onclick="CopyToClipboard('tag31633');return false;" class="tag-decoration">testing-v5</div><div id="tag22619" onclick="CopyToClipboard('tag22619');return false;" class="tag-decoration">testing-v5.0</div><div id="tag13521" onclick="CopyToClipboard('tag13521');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5fd627228d81b49e236e2a338d01d89f99664375" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/28979412430" target="_blank">2026-07-08 22:13:27</a></td></tr>
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
