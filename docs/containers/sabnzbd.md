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
<tr><td><div id="tag19688" onclick="CopyToClipboard('tag19688');return false;" class="tag-decoration">nightly</div><div id="tag2591" onclick="CopyToClipboard('tag2591');return false;" class="tag-decoration">nightly-8e4feee</div><div id="tag30243" onclick="CopyToClipboard('tag30243');return false;" class="tag-decoration">nightly-25d20f0f08ce2078402faf0e7b281db9ceb04643</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/8e4feee37519b0a282360dc599102358a15feaa3" target="_blank">chore(build): add dockerfile syntax + check directives--Mirror hotio/caddy@39f3ebf: pin BuildKit frontend and skip-InvalidDefaultArgInFrom warning for ARG UPSTREAM_* in FROM.</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26359237304" target="_blank">2026-05-24 10:51:28</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag7901" onclick="CopyToClipboard('tag7901');return false;" class="tag-decoration">release</div><div id="tag8869" onclick="CopyToClipboard('tag8869');return false;" class="tag-decoration">release-87d3296</div><div id="tag11200" onclick="CopyToClipboard('tag11200');return false;" class="tag-decoration">release-5.0.3</div><div id="tag21489" onclick="CopyToClipboard('tag21489');return false;" class="tag-decoration">release-v5</div><div id="tag2563" onclick="CopyToClipboard('tag2563');return false;" class="tag-decoration">release-v5.0</div><div id="tag29132" onclick="CopyToClipboard('tag29132');return false;" class="tag-decoration">release-v5.0.3</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/87d32964b6cf299c271e4a59446bb0d133fa03bc" target="_blank">chore(build): add dockerfile syntax + check directives--Mirror hotio/caddy@39f3ebf: pin BuildKit frontend and skip-InvalidDefaultArgInFrom warning for ARG UPSTREAM_* in FROM.</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26359232002" target="_blank">2026-05-24 10:51:10</a></td></tr>
<tr><td><div id="tag24836" onclick="CopyToClipboard('tag24836');return false;" class="tag-decoration">testing</div><div id="tag10354" onclick="CopyToClipboard('tag10354');return false;" class="tag-decoration">testing-8cb8081</div><div id="tag23903" onclick="CopyToClipboard('tag23903');return false;" class="tag-decoration">testing-5.0.3</div><div id="tag10410" onclick="CopyToClipboard('tag10410');return false;" class="tag-decoration">testing-v5</div><div id="tag14160" onclick="CopyToClipboard('tag14160');return false;" class="tag-decoration">testing-v5.0</div><div id="tag11837" onclick="CopyToClipboard('tag11837');return false;" class="tag-decoration">testing-v5.0.3</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/8cb8081bf0434dd07e454648cad1d85a1dabe307" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/26360698426" target="_blank">2026-05-24 12:02:19</a></td></tr>
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
