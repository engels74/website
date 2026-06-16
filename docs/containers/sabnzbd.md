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
<tr><td><div id="tag16279" onclick="CopyToClipboard('tag16279');return false;" class="tag-decoration">nightly</div><div id="tag6792" onclick="CopyToClipboard('tag6792');return false;" class="tag-decoration">nightly-8caaeaf</div><div id="tag16904" onclick="CopyToClipboard('tag16904');return false;" class="tag-decoration">nightly-89e8788b0300009f12395b356526c761acc831f1</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/8caaeaff732ea4ce022a6290900bec7e177235ad" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27630686034" target="_blank">2026-06-16 15:59:03</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag5784" onclick="CopyToClipboard('tag5784');return false;" class="tag-decoration">release</div><div id="tag7906" onclick="CopyToClipboard('tag7906');return false;" class="tag-decoration">release-746e018</div><div id="tag11944" onclick="CopyToClipboard('tag11944');return false;" class="tag-decoration">release-5.0.4</div><div id="tag32189" onclick="CopyToClipboard('tag32189');return false;" class="tag-decoration">release-v5</div><div id="tag23093" onclick="CopyToClipboard('tag23093');return false;" class="tag-decoration">release-v5.0</div><div id="tag3782" onclick="CopyToClipboard('tag3782');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/746e018cd50910dae73acbd4ab2ae90183233d6c" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354913378" target="_blank">2026-06-11 14:40:57</a></td></tr>
<tr><td><div id="tag23599" onclick="CopyToClipboard('tag23599');return false;" class="tag-decoration">testing</div><div id="tag5555" onclick="CopyToClipboard('tag5555');return false;" class="tag-decoration">testing-1b1942e</div><div id="tag12267" onclick="CopyToClipboard('tag12267');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag24975" onclick="CopyToClipboard('tag24975');return false;" class="tag-decoration">testing-v5</div><div id="tag23811" onclick="CopyToClipboard('tag23811');return false;" class="tag-decoration">testing-v5.0</div><div id="tag4903" onclick="CopyToClipboard('tag4903');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/1b1942e349033b72b39f15958dc0694493b2d37d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27354916499" target="_blank">2026-06-11 14:40:59</a></td></tr>
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
