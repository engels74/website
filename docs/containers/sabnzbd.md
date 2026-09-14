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
<tr><td><div id="tag1483" onclick="CopyToClipboard('tag1483');return false;" class="tag-decoration">nightly</div><div id="tag20740" onclick="CopyToClipboard('tag20740');return false;" class="tag-decoration">nightly-593eb4a</div><div id="tag3098" onclick="CopyToClipboard('tag3098');return false;" class="tag-decoration">nightly-2a30c7fc3c643362e447afb5a2706bc3fa226205</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/593eb4a74beb627d7b2d7e5eb1637f6d3af1c598" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34832991799" target="_blank">2026-09-14 10:24:08</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag3582" onclick="CopyToClipboard('tag3582');return false;" class="tag-decoration">release</div><div id="tag16685" onclick="CopyToClipboard('tag16685');return false;" class="tag-decoration">release-7f49c81</div><div id="tag10167" onclick="CopyToClipboard('tag10167');return false;" class="tag-decoration">release-5.1.3</div><div id="tag22884" onclick="CopyToClipboard('tag22884');return false;" class="tag-decoration">release-v5</div><div id="tag10591" onclick="CopyToClipboard('tag10591');return false;" class="tag-decoration">release-v5.1</div><div id="tag5863" onclick="CopyToClipboard('tag5863');return false;" class="tag-decoration">release-v5.1.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7f49c8193cfd6e4bfb7d1d5f6ec8325d3ab09c27" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482526229" target="_blank">2026-09-10 13:25:12</a></td></tr>
<tr><td><div id="tag19462" onclick="CopyToClipboard('tag19462');return false;" class="tag-decoration">testing</div><div id="tag24910" onclick="CopyToClipboard('tag24910');return false;" class="tag-decoration">testing-ffe78cf</div><div id="tag26310" onclick="CopyToClipboard('tag26310');return false;" class="tag-decoration">testing-5.1.3</div><div id="tag5704" onclick="CopyToClipboard('tag5704');return false;" class="tag-decoration">testing-v5</div><div id="tag15350" onclick="CopyToClipboard('tag15350');return false;" class="tag-decoration">testing-v5.1</div><div id="tag14634" onclick="CopyToClipboard('tag14634');return false;" class="tag-decoration">testing-v5.1.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/ffe78cf751803bd92188cb006e353d499184f818" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/34482510601" target="_blank">2026-09-10 13:25:03</a></td></tr>
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
