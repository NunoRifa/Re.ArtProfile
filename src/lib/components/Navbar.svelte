<script>
  import { each } from "svelte/internal";
  import MediaQuery from "./MediaQuery.svelte";

  const menu = [
    {
      id: 1,
      menu: "Our Journey",
      url: "",
    },
    {
      id: 2,
      menu: "Achievements",
      url: "",
    },
    {
      id: 3,
      menu: "Our Team",
      url: "",
    },
  ];

  let expand = false;
</script>

<MediaQuery query="(min-width: 1024px)" let:matches>
  {#if matches}
    <div class="navbar">
      <div class="container">
        <div class="nav-component">
          <div class="logo">Re.Art</div>
          <div class="menu">
            {#each menu as m}
              <a href={m.url} class="menu-link">{m.menu}</a>
            {/each}
          </div>
          <div class="contact-us">Contact us</div>
        </div>
      </div>
    </div>
  {:else}
    <div class="navbar">
      <div class="container">
        <div class="nav-component">
          <div class="logo">Re.Art</div>
          <div class="toggle">
            <div
              class="hamburger {expand ? 'active' : ''}"
              on:click={() => {
                expand = !expand;
              }}
            >
              <span class="line" />
              <span class="line" />
              <span class="line" />
            </div>
          </div>
        </div>
      </div>
      {#if expand}
        <div class="menu">
          <div class="container">
            {#each menu as m}
              <a href={m.url} class="menu-link">{m.menu}</a>
            {/each}
          </div>
        </div>
      {/if}
      {#if expand}
        <div
          class="overlay-bg"
          on:click={() => {
            expand = !expand;
          }}
        />
      {/if}
    </div>
  {/if}
</MediaQuery>

<style lang="scss">
  .navbar {
    display: block;
    width: 100%;
    height: 106px;
    background: $primary-bg;
    z-index: 9999;

    .nav-component {
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      padding: 31px 0;

      .logo {
        color: $text-white;
        font-size: 32px;
        font-weight: 700;
      }

      .menu {
        .menu-link {
          display: inline-block;
          padding: 5px 35px;
          color: #a0a1a2;
          font-weight: 700;
        }

        .menu-link:hover {
          color: $text-white;
          transition: 0.2s;
        }
      }

      .contact-us {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        width: 150px;
        height: 50px;
        border-radius: 50px;
        background: #1155d9;
        text-align: center;
        color: $text-white;
        font-weight: 700;
      }

      .contact-us:hover {
        background: #0d47bb;
      }
    }
  }

  @media screen and (max-width: 768px) {
    .navbar {
      position: fixed;
      height: 60px;

      .nav-component {
        position: relative;
        justify-content: center;
        padding: 15px 0px;

        .logo {
          font-size: 20px;
        }

        .toggle {
          position: absolute;
          right: 0;

          .hamburger {
            background: transparent;
            border: none;
            outline: none;
            cursor: pointer;

            .line {
              display: block;
              width: 20px;
              height: 2px;
              background: $secondary-bg;
              margin-block: 6px;
              border-radius: 5px;
              transition: transform 0.5s;
              opacity: 0.25s;
            }
          }

          .hamburger.active {
            .line:nth-child(1) {
              transform: translateY(6px) rotate(45deg);
            }

            .line:nth-child(2) {
              opacity: 0;
            }

            .line:nth-child(3) {
              transform: translateY(-10px) rotate(-45deg);
            }
          }
        }
      }

      .menu {
        width: 100%;
        background: #232528;
        position: fixed;
        z-index: 99;
      }

      .menu > .container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;

        a.menu-link {
          font-size: 12px;
          font-weight: 700;
          padding: 15px 0;
        }

        a.menu-link:nth-child(1) {
          margin-top: 15px;
        }

        a.menu-link:nth-last-child(1) {
          margin-bottom: 15px;
        }
      }

      .overlay-bg {
        position: fixed;
        display: block;
        width: 100vw;
        height: 100vh;
        background: rgba(0, 0, 0, 0.6);
        z-index: 9;
      }
    }
  }
</style>
