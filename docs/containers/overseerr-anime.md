---
hide:
  - toc
title: engels74/overseerr-anime
---

[:octicons-mark-github-16: GitHub](https://github.com/engels74/overseerr-anime){ class="header-links" target="_blank" rel="noopener" }
[:octicons-container-16: ghcr.io](https://github.com/orgs/engels74/packages/container/package/overseerr-anime){ class="header-links" target="_blank" rel="noopener" }

[:octicons-link-16: Upstream Project](https://github.com/sct/overseerr){ class="header-links" target="_blank" rel="noopener" }

<div class="image-logo"><img src="https://i.imgur.com/BcvImhI.png" alt="logo"></div>

!!! question "What is this?"

    This is a fork of Hotio's [overseerr](https://hotio.dev/containers/overseerr) Docker image, that includes the [Anime Instance PR (#3664)](https://github.com/sct/overseerr/pull/3664).

    It's built using [this fork of the PR](https://github.com/engels74/overseerr-anime-source).

!!! note "Branches and Tags"

    This project maintains two branches, each with its own Docker tag:

    - **`:release` (or `:latest`)**:
      Based on the [`feature-default-anime-instance-checkbox-release`](https://github.com/engels74/overseerr-anime-source/tree/feature-default-anime-instance-checkbox-release) branch.
      This is the stable version, rebased from the `sct/overseerr` repository's `master` branch (official releases) with the anime instance support changes applied.

???+ info "Why is this needed?"

    This was made since Overseerr maintainers are [very busy](https://discord.com/channels/783137440809746482/785475251231784961/1262212831579996285), and it probably won't get merged in the near future.

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
<tr><td><div class="tag-decoration-latest">latest</div><div id="tag30855" onclick="CopyToClipboard('tag30855');return false;" class="tag-decoration">release</div><div id="tag19057" onclick="CopyToClipboard('tag19057');return false;" class="tag-decoration">release-1710aeb</div><div id="tag12405" onclick="CopyToClipboard('tag12405');return false;" class="tag-decoration">release-1.34.0-anime</div><div id="tag1611" onclick="CopyToClipboard('tag1611');return false;" class="tag-decoration">release-v1</div><div id="tag26537" onclick="CopyToClipboard('tag26537');return false;" class="tag-decoration">release-v1.34</div><div id="tag116" onclick="CopyToClipboard('tag116');return false;" class="tag-decoration">release-v1.34.0</div></td><td>Releases</td><td><a href="https://github.com/engels74/overseerr-anime/commit/1710aeb25ade342be8a7f0908e4a3d8b081142c2" target="_blank">Upstream update: alpinevpn-8258b00 => alpinevpn-fe778dd</a></td><td><a href="https://github.com/engels74/overseerr-anime/actions/runs/21389826759" target="_blank">2026-01-27 08:23:26</a></td></tr>
</tbody>
  </table>
</div>

## Starting the container

=== "cli"

    ```shell linenums="1"
    docker run --rm \
        --name overseerr-anime \
        -p 5055:5055 \
        -e PUID=1000 \
        -e PGID=1000 \
        -e UMASK=002 \
        -e TZ="Etc/UTC" \
        -e WEBUI_PORTS="5055/tcp,5055/udp" \
        -v /<host_folder_config>:/config \
        ghcr.io/engels74/overseerr-anime
    ```

=== "compose"

    ```yaml linenums="1"
    services:
      overseerr-anime:
        container_name: overseerr-anime
        image: ghcr.io/engels74/overseerr-anime
        ports:
          - "5055:5055"
        environment:
          - PUID=1000
          - PGID=1000
          - UMASK=002
          - TZ=Etc/UTC
          - WEBUI_PORTS=5055/tcp,5055/udp
        volumes:
          - /<host_folder_config>:/config
    ```

--8<-- "includes/wireguard.md"
