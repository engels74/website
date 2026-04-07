---
hide:
  - toc
title: engels74/qflood
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/qflood){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/qflood){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/jesec/flood){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="/img/image-logos/qflood.svg" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [rflood](https://hotio.dev/containers/rflood) Docker image, that uses qBittorrent instead of rtorrent. The qflood image has both "releases" and "nightly support". The included [qBittorrent](https://github.com/userdocs/qbittorrent-nox-static) uses libtorrent v2.x.

???+ info "What is nightly?"

    Nightly means it updates automatically after a successful run of [this workflow file](https://github.com/jesec/flood/actions/workflows/publish-rolling.yml). This means that whenever the official flood repository receives a push commit, this docker image should automatically be updated. All thanks to hotio's brilliant setup.

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
<tr><td><div id="tag28516" onclick="CopyToClipboard('tag28516');return false;" class="tag-decoration">nightly</div><div id="tag26025" onclick="CopyToClipboard('tag26025');return false;" class="tag-decoration">nightly-395ccc3</div><div id="tag29465" onclick="CopyToClipboard('tag29465');return false;" class="tag-decoration">nightly-5.1.4--24081870535</div><div id="tag9179" onclick="CopyToClipboard('tag9179');return false;" class="tag-decoration">nightly-v5</div><div id="tag3786" onclick="CopyToClipboard('tag3786');return false;" class="tag-decoration">nightly-v5.1</div><div id="tag602" onclick="CopyToClipboard('tag602');return false;" class="tag-decoration">nightly-v5.1.4</div></td><td>nightly</td><td><a href="https://github.com/engels74/qflood/commit/395ccc365e7e00aca2abbcd9280ba2386a7adbe9" target="_blank">Version update: 5.1.4--24023730946 => 5.1.4--24081870535</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/24085379723" target="_blank">2026-04-07 13:59:27</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag820" onclick="CopyToClipboard('tag820');return false;" class="tag-decoration">release</div><div id="tag8400" onclick="CopyToClipboard('tag8400');return false;" class="tag-decoration">release-1377700</div><div id="tag11460" onclick="CopyToClipboard('tag11460');return false;" class="tag-decoration">release-5.1.4--4.13.7</div><div id="tag8507" onclick="CopyToClipboard('tag8507');return false;" class="tag-decoration">release-v5</div><div id="tag25774" onclick="CopyToClipboard('tag25774');return false;" class="tag-decoration">release-v5.1</div><div id="tag8154" onclick="CopyToClipboard('tag8154');return false;" class="tag-decoration">release-v5.1.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/qflood/commit/1377700e4caa6b0771994ab2f39b6217aeb6bd11" target="_blank">Version update: 5.1.4--4.13.7 => 5.1.4--4.13.7</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/24085380212" target="_blank">2026-04-07 13:59:28</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name qflood \
        -p 8080:8080 \
        -p 3000:3000 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e LIBTORRENT="v2" \
        -e FLOOD_AUTH="true" \
        -e ARGS="" \
        -e FLOOD_ARGS="" \
        -v /<host_folder_config>:/config \
        -v /<host_folder_data>:/data \
        ghcr.io/engels74/qflood
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      qflood:
        container_name: qflood
        image: ghcr.io/engels74/qflood
        ports:
          - "8080:8080"
          - "3000:3000"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - LIBTORRENT=v2
          - FLOOD_AUTH=true
          - ARGS
          - FLOOD_ARGS
        volumes:
          - /<host_folder_config>:/config
          - /<host_folder_data>:/data
    ```

## Changing the WebUI port

Under certain circumstances it's required to run the WebUI on a different internal port, you can do that by modifying the environment variable `WEBUI_PORTS` accordingly. It should be in the format `xxxx/tcp,xxxx/udp`, take a look at the default with `docker logs` (variable is printed at container start) or `docker inspect`.

--8<-- "includes/wireguard.md"
