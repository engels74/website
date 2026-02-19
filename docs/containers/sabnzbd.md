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
<tr><td><div id="tag28890" onclick="CopyToClipboard('tag28890');return false;" class="tag-decoration">nightly</div><div id="tag31385" onclick="CopyToClipboard('tag31385');return false;" class="tag-decoration">nightly-4e4bf67</div><div id="tag4493" onclick="CopyToClipboard('tag4493');return false;" class="tag-decoration">nightly-bc4c4bbcfaaadfc09ef2bddfe3f95b17c0214c1b</div></td><td>Every commit to develop</td><td><a href="https://github.com/engels74/sabnzbd/commit/4e4bf67001ebb046888546356d9c5eb35d56d1d2" target="_blank">Version update: 33072154d215cc7b4de6c500b9102a88d9640eb1 => bc4c4bbcfaaadfc09ef2bddfe3f95b17c0214c1b</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/22203679127" target="_blank">2026-02-19 22:59:15</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag22278" onclick="CopyToClipboard('tag22278');return false;" class="tag-decoration">release</div><div id="tag16019" onclick="CopyToClipboard('tag16019');return false;" class="tag-decoration">release-252442e</div><div id="tag28179" onclick="CopyToClipboard('tag28179');return false;" class="tag-decoration">release-4.5.5</div><div id="tag2096" onclick="CopyToClipboard('tag2096');return false;" class="tag-decoration">release-v4</div><div id="tag16297" onclick="CopyToClipboard('tag16297');return false;" class="tag-decoration">release-v4.5</div><div id="tag20056" onclick="CopyToClipboard('tag20056');return false;" class="tag-decoration">release-v4.5.5</div></td><td>Releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/252442ee081e7bffb07db68d74238fe65fe61492" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823272944" target="_blank">2026-02-09 11:29:10</a></td></tr>
<tr><td><div id="tag23662" onclick="CopyToClipboard('tag23662');return false;" class="tag-decoration">testing</div><div id="tag5487" onclick="CopyToClipboard('tag5487');return false;" class="tag-decoration">testing-3dc0cdf</div><div id="tag30370" onclick="CopyToClipboard('tag30370');return false;" class="tag-decoration">testing-4.5.5</div><div id="tag6546" onclick="CopyToClipboard('tag6546');return false;" class="tag-decoration">testing-v4</div><div id="tag20154" onclick="CopyToClipboard('tag20154');return false;" class="tag-decoration">testing-v4.5</div><div id="tag13510" onclick="CopyToClipboard('tag13510');return false;" class="tag-decoration">testing-v4.5.5</div></td><td>Pre-releases</td><td><a href="https://github.com/engels74/sabnzbd/commit/3dc0cdf9be0128f86ab1d3137f11ee412fbc5fa6" target="_blank">Version update: 4.5.5 => 4.5.5</a></td><td><a href="https://github.com/engels74/sabnzbd/actions/runs/21823273556" target="_blank">2026-02-09 11:29:12</a></td></tr>
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
