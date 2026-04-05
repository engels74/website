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
<tr><td><div id="tag18374" onclick="CopyToClipboard('tag18374');return false;" class="tag-decoration">nightly</div><div id="tag5825" onclick="CopyToClipboard('tag5825');return false;" class="tag-decoration">nightly-ae9c5ff</div><div id="tag16012" onclick="CopyToClipboard('tag16012');return false;" class="tag-decoration">nightly-5.1.4--24003166369</div><div id="tag27139" onclick="CopyToClipboard('tag27139');return false;" class="tag-decoration">nightly-v5</div><div id="tag21818" onclick="CopyToClipboard('tag21818');return false;" class="tag-decoration">nightly-v5.1</div><div id="tag24287" onclick="CopyToClipboard('tag24287');return false;" class="tag-decoration">nightly-v5.1.4</div></td><td>nightly</td><td><a href="https://github.com/engels74/qflood/commit/ae9c5ff8b9241cfd774f30a73e047f4bd9d34392" target="_blank">Version update: 5.1.4--23633484239 => 5.1.4--24003166369</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/24003564559" target="_blank">2026-04-05 14:29:48</a></td></tr>
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag10856" onclick="CopyToClipboard('tag10856');return false;" class="tag-decoration">release</div><div id="tag12515" onclick="CopyToClipboard('tag12515');return false;" class="tag-decoration">release-f8715de</div><div id="tag10494" onclick="CopyToClipboard('tag10494');return false;" class="tag-decoration">release-5.1.4--4.13.7</div><div id="tag19576" onclick="CopyToClipboard('tag19576');return false;" class="tag-decoration">release-v5</div><div id="tag8504" onclick="CopyToClipboard('tag8504');return false;" class="tag-decoration">release-v5.1</div><div id="tag25164" onclick="CopyToClipboard('tag25164');return false;" class="tag-decoration">release-v5.1.4</div></td><td>Releases</td><td><a href="https://github.com/engels74/qflood/commit/f8715debdfff9e1ce9539f5b825b78967340a497" target="_blank">Version update: 5.1.4--4.13.0 => 5.1.4--4.13.7</a></td><td><a href="https://github.com/engels74/qflood/actions/runs/24003565153" target="_blank">2026-04-05 14:29:50</a></td></tr>
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
