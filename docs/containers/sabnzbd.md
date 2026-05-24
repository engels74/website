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
<tr><td><div id="tag16315" onclick="CopyToClipboard('tag16315');return false;" class="tag-decoration">nightly</div><div id="tag30389" onclick="CopyToClipboard('tag30389');return false;" class="tag-decoration">nightly-8e4feee</div><div id="tag29078" onclick="CopyToClipboard('tag29078');return false;" class="tag-decoration">nightly-25d20f0f08ce2078402faf0e7b281db9ceb04643</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/8e4feee37519b0a282360dc599102358a15feaa3" target="_blank">chore(build): add dockerfile syntax + check directives--Mirror hotio/caddy@39f3ebf: pin BuildKit frontend and skip-InvalidDefaultArgInFrom warning for ARG UPSTREAM_* in FROM.</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26359237304" target="_blank">2026-05-24 10:51:28</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag19052" onclick="CopyToClipboard('tag19052');return false;" class="tag-decoration">release</div><div id="tag17870" onclick="CopyToClipboard('tag17870');return false;" class="tag-decoration">release-87d3296</div><div id="tag26692" onclick="CopyToClipboard('tag26692');return false;" class="tag-decoration">release-5.0.3</div><div id="tag1132" onclick="CopyToClipboard('tag1132');return false;" class="tag-decoration">release-v5</div><div id="tag9950" onclick="CopyToClipboard('tag9950');return false;" class="tag-decoration">release-v5.0</div><div id="tag451" onclick="CopyToClipboard('tag451');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/87d32964b6cf299c271e4a59446bb0d133fa03bc" target="_blank">chore(build): add dockerfile syntax + check directives--Mirror hotio/caddy@39f3ebf: pin BuildKit frontend and skip-InvalidDefaultArgInFrom warning for ARG UPSTREAM_* in FROM.</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26359232002" target="_blank">2026-05-24 10:51:10</a></td></tr>
<tr><td><div id="tag31441" onclick="CopyToClipboard('tag31441');return false;" class="tag-decoration">testing</div><div id="tag20260" onclick="CopyToClipboard('tag20260');return false;" class="tag-decoration">testing-31fa7f7</div><div id="tag15440" onclick="CopyToClipboard('tag15440');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag28465" onclick="CopyToClipboard('tag28465');return false;" class="tag-decoration">testing-v5</div><div id="tag4248" onclick="CopyToClipboard('tag4248');return false;" class="tag-decoration">testing-v5.0</div><div id="tag23444" onclick="CopyToClipboard('tag23444');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/31fa7f7dfec042547696a92de39aa167d4611061" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26352501722" target="_blank">2026-05-24 05:03:34</a></td></tr>
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
