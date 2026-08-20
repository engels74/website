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
<tr><td><div id="tag5143" onclick="CopyToClipboard('tag5143');return false;" class="tag-decoration">nightly</div><div id="tag27402" onclick="CopyToClipboard('tag27402');return false;" class="tag-decoration">nightly-e59781b</div><div id="tag10881" onclick="CopyToClipboard('tag10881');return false;" class="tag-decoration">nightly-21d639bf5ff898e05dd48ee08ca76b63e20046a5</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/e59781b3a9adf81b00fc3a381803f258439d1acb" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32326594708" target="_blank">2026-08-20 02:59:12</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag16622" onclick="CopyToClipboard('tag16622');return false;" class="tag-decoration">release</div><div id="tag23554" onclick="CopyToClipboard('tag23554');return false;" class="tag-decoration">release-873c6ed</div><div id="tag15728" onclick="CopyToClipboard('tag15728');return false;" class="tag-decoration">release-5.1.1</div><div id="tag28571" onclick="CopyToClipboard('tag28571');return false;" class="tag-decoration">release-v5</div><div id="tag27480" onclick="CopyToClipboard('tag27480');return false;" class="tag-decoration">release-v5.1</div><div id="tag27312" onclick="CopyToClipboard('tag27312');return false;" class="tag-decoration">release-v5.1.1</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/873c6ed5689805d5601041c4366ba4dce463610d" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32326594493" target="_blank">2026-08-20 02:59:11</a></td></tr>
<tr><td><div id="tag22513" onclick="CopyToClipboard('tag22513');return false;" class="tag-decoration">testing</div><div id="tag14022" onclick="CopyToClipboard('tag14022');return false;" class="tag-decoration">testing-d8668cf</div><div id="tag29529" onclick="CopyToClipboard('tag29529');return false;" class="tag-decoration">testing-5.1.1</div><div id="tag6457" onclick="CopyToClipboard('tag6457');return false;" class="tag-decoration">testing-v5</div><div id="tag6881" onclick="CopyToClipboard('tag6881');return false;" class="tag-decoration">testing-v5.1</div><div id="tag10921" onclick="CopyToClipboard('tag10921');return false;" class="tag-decoration">testing-v5.1.1</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/d8668cf332ab4769bfd394685457fc263c854c78" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/32326597320" target="_blank">2026-08-20 02:59:14</a></td></tr>
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
