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
<tr><td><div id="tag29063" onclick="CopyToClipboard('tag29063');return false;" class="tag-decoration">nightly</div><div id="tag28617" onclick="CopyToClipboard('tag28617');return false;" class="tag-decoration">nightly-8862823</div><div id="tag27646" onclick="CopyToClipboard('tag27646');return false;" class="tag-decoration">nightly-4a999a19081b76cff813b1c0e13bfea2234f314a</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/886282368a599462f970d930781831b9db2c8585" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33557241672" target="_blank">2026-09-01 20:46:07</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag29828" onclick="CopyToClipboard('tag29828');return false;" class="tag-decoration">release</div><div id="tag32530" onclick="CopyToClipboard('tag32530');return false;" class="tag-decoration">release-a1855af</div><div id="tag32598" onclick="CopyToClipboard('tag32598');return false;" class="tag-decoration">release-5.1.2</div><div id="tag18508" onclick="CopyToClipboard('tag18508');return false;" class="tag-decoration">release-v5</div><div id="tag32324" onclick="CopyToClipboard('tag32324');return false;" class="tag-decoration">release-v5.1</div><div id="tag30022" onclick="CopyToClipboard('tag30022');return false;" class="tag-decoration">release-v5.1.2</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/a1855afac8dca1731428166af3e688a589ebb604" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33512344853" target="_blank">2026-09-01 13:15:54</a></td></tr>
<tr><td><div id="tag24299" onclick="CopyToClipboard('tag24299');return false;" class="tag-decoration">testing</div><div id="tag8383" onclick="CopyToClipboard('tag8383');return false;" class="tag-decoration">testing-7c58157</div><div id="tag17445" onclick="CopyToClipboard('tag17445');return false;" class="tag-decoration">testing-5.1.2</div><div id="tag2035" onclick="CopyToClipboard('tag2035');return false;" class="tag-decoration">testing-v5</div><div id="tag20889" onclick="CopyToClipboard('tag20889');return false;" class="tag-decoration">testing-v5.1</div><div id="tag8689" onclick="CopyToClipboard('tag8689');return false;" class="tag-decoration">testing-v5.1.2</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/7c58157bc5142215d27c34672a7813bc021e3ec0" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/33512331417" target="_blank">2026-09-01 13:15:45</a></td></tr>
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
