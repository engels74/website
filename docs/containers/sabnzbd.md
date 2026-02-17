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
<tr><td><div id="tag20702" onclick="CopyToClipboard('tag20702');return false;" class="tag-decoration">nightly</div><div id="tag22169" onclick="CopyToClipboard('tag22169');return false;" class="tag-decoration">nightly-530090c</div><div id="tag23012" onclick="CopyToClipboard('tag23012');return false;" class="tag-decoration">nightly-33072154d215cc7b4de6c500b9102a88d9640eb1</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/530090cb8fed6877f1e07042915a92987c522532" target="_blank">Version update: d7b7377b42763f7f656afe19c24472d4fb0aac14 => 33072154d215cc7b4de6c500b9102a88d9640eb1</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22104761269" target="_blank">2026-02-17 15:35:19</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag2601" onclick="CopyToClipboard('tag2601');return false;" class="tag-decoration">release</div><div id="tag7776" onclick="CopyToClipboard('tag7776');return false;" class="tag-decoration">release-252442e</div><div id="tag26340" onclick="CopyToClipboard('tag26340');return false;" class="tag-decoration">release-4.5.5</div><div id="tag17831" onclick="CopyToClipboard('tag17831');return false;" class="tag-decoration">release-v4</div><div id="tag21828" onclick="CopyToClipboard('tag21828');return false;" class="tag-decoration">release-v4.5</div><div id="tag8129" onclick="CopyToClipboard('tag8129');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/252442ee081e7bffb07db68d74238fe65fe61492" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823272944" target="_blank">2026-02-09 11:29:10</a></td></tr>
<tr><td><div id="tag24139" onclick="CopyToClipboard('tag24139');return false;" class="tag-decoration">testing</div><div id="tag7921" onclick="CopyToClipboard('tag7921');return false;" class="tag-decoration">testing-3dc0cdf</div><div id="tag2849" onclick="CopyToClipboard('tag2849');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag28809" onclick="CopyToClipboard('tag28809');return false;" class="tag-decoration">testing-v4</div><div id="tag22871" onclick="CopyToClipboard('tag22871');return false;" class="tag-decoration">testing-v4.5</div><div id="tag24572" onclick="CopyToClipboard('tag24572');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3dc0cdf9be0128f86ab1d3137f11ee412fbc5fa6" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823273556" target="_blank">2026-02-09 11:29:12</a></td></tr>
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
