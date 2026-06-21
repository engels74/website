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
<tr><td><div id="tag7472" onclick="CopyToClipboard('tag7472');return false;" class="tag-decoration">nightly</div><div id="tag5801" onclick="CopyToClipboard('tag5801');return false;" class="tag-decoration">nightly-06cbc99</div><div id="tag23421" onclick="CopyToClipboard('tag23421');return false;" class="tag-decoration">nightly-7daa0159ec76fdee6bcfa81620a4300aee924d40</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/06cbc99315a71b51d2a67fabb6f1f4861f09362e" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27915529054" target="_blank">2026-06-21 19:48:19</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag1835" onclick="CopyToClipboard('tag1835');return false;" class="tag-decoration">release</div><div id="tag5302" onclick="CopyToClipboard('tag5302');return false;" class="tag-decoration">release-776e678</div><div id="tag9840" onclick="CopyToClipboard('tag9840');return false;" class="tag-decoration">release-5.0.4</div><div id="tag2277" onclick="CopyToClipboard('tag2277');return false;" class="tag-decoration">release-v5</div><div id="tag815" onclick="CopyToClipboard('tag815');return false;" class="tag-decoration">release-v5.0</div><div id="tag25803" onclick="CopyToClipboard('tag25803');return false;" class="tag-decoration">release-v5.0.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/776e678fe2d168b2e311463b46288f7b57d2e26f" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27873973790" target="_blank">2026-06-20 14:25:37</a></td></tr>
<tr><td><div id="tag16694" onclick="CopyToClipboard('tag16694');return false;" class="tag-decoration">testing</div><div id="tag9998" onclick="CopyToClipboard('tag9998');return false;" class="tag-decoration">testing-5996b41</div><div id="tag9521" onclick="CopyToClipboard('tag9521');return false;" class="tag-decoration">testing-5.0.4</div><div id="tag22032" onclick="CopyToClipboard('tag22032');return false;" class="tag-decoration">testing-v5</div><div id="tag13314" onclick="CopyToClipboard('tag13314');return false;" class="tag-decoration">testing-v5.0</div><div id="tag30570" onclick="CopyToClipboard('tag30570');return false;" class="tag-decoration">testing-v5.0.4</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/5996b411ad9a9b78f21bf3d1ff849271e6578a00" target="_blank">Modified: meta.json</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/27873975239" target="_blank">2026-06-20 14:25:41</a></td></tr>
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
