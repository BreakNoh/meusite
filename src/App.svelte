<script lang="ts">
    import Foto from "./assets/minha_foto.jpg";
    import IconeEMail from "./lib/IconeEMail.svelte";
    import IconeGH from "./lib/IconeGH.svelte";
    import CMDLine from "./lib/CMDLine.svelte";
</script>

<main>
    <div class="sobre-mim conteiner">
        <img src={Foto} alt="foto minha" style="grid-area: fot" />

        <div class="infos">
            <div class="vulgo">
                <CMDLine
                    cursor={false}
                    cifrao={false}
                    tokens={[
                        ["export ", "palavra-chave"],
                        [" ", "espaco"],
                        ["BRENO", "variavel"],
                        ["=", "operador"],
                        ['"BreakNoh"', "primitivo"],
                    ]}
                />
            </div>
            <h1 style="grid-area: sau">
                <CMDLine
                    cursor={false}
                    tokens={[
                        ["echo", "palavra-chave"],
                        [" ", "espaco"],
                        ["\\", "operador"],
                    ]}
                />
                <br />
                <CMDLine
                    cursor={true}
                    cifrao={false}
                    tokens={[
                        ['"oi, eu sou o', "primitivo"],
                        [" ", "espaco"],
                        ["$BRENO", "variavel"],
                        ['"', "primitivo"],
                    ]}
                />
            </h1>
            <h2>
                <CMDLine
                    tokens={[
                        ["cat", "palavra-chave"],
                        [" ", "espaco"],
                        ["sobre-mim.md", "primitivo"],
                    ]}
                />
            </h2>
            <p>
                Sou um dev entusiasta, e desejo poder trabalhar na área. Gosto
                de conhecer tecnologias novas, e me desafiar a me manter
                criativo e inovador.
            </p>
        </div>
    </div>

    <div class="projetos conteiner">
        <h2>
            <CMDLine
                tokens={[
                    ["ls", "palavra-chave"],
                    [" ", "espaco"],
                    ["meus-projetos", "primitivo"],
                ]}
            />
        </h2>
        <ul>
            <div class="cartao">
                <div class="conteudo">
                    <h3>
                        <a href="https://github.com/BreakNoh/obinus">
                            <CMDLine
                                cifrao={false}
                                cursor={false}
                                tokens={[
                                    [">", "operador"],
                                    [" ", "espaco"],
                                    ["obinus", "primitivo"],
                                ]}
                            />
                        </a>
                    </h3>
                    <p>
                        coleção de raspadores de horários de ônibus de todo
                        território de SC
                    </p>
                </div>
                <a href="https://github.com/BreakNoh/obinus">ver mais</a>
            </div>
            <div class="cartao">
                <div class="conteudo">
                    <h3>
                        <a href="https://github.com/BreakNoh/tet_rs">
                            <CMDLine
                                cifrao={false}
                                cursor={false}
                                tokens={[
                                    [">", "operador"],
                                    [" ", "espaco"],
                                    ["tet_rs", "primitivo"],
                                ]}
                            />
                        </a>
                    </h3>
                    <p>engine de tetris para o terminal escrita em rust</p>
                </div>
                <a href="https://github.com/BreakNoh/tet_rs">ver mais</a>
            </div>
        </ul>
    </div>
</main>

<footer>
    <div class="espacador"></div>

    <div class="sociais">
        <div>
            <CMDLine
                tokens={[
                    ["ls", "palavra-chave"],
                    [" ", "espaco"],
                    ["socials", "primitivo"],
                ]}
            />
        </div>
        <div class="links">
            <a href="https://github.com/BreakNoh" class="link-social"
                ><IconeGH />github</a
            >
            <a href="mailto://eu@bre.dev.br" class="link-social"
                ><IconeEMail />contato</a
            >
        </div>
    </div>

    <div class="wrap-cod-fonte">
        <a href="https://github.com/BreakNoh/meusite" class="cod-fonte">
            código fonte
        </a>
    </div>
</footer>

<style>
    main {
        margin-top: max(2vh, 1rem);

        margin-inline: clamp(1rem, 15%, 30rem);
        @media screen and (width <= 950px) {
            margin-inline: clamp(0.5rem, 5%, 5rem);
        }
    }
    p {
        color: white;
        max-width: 30rem;
    }
    h1 {
        margin-block: 0.5rem 1rem;
        font-size: clamp(16px, 5vw, 32px);
    }
    h2 {
        margin-block: 1rem 0.5rem;
        font-size: clamp(8px, 5vw, 24px);
    }
    h3 {
        font-size: clamp(8px, 5vw, 24px);
    }
    img {
        aspect-ratio: 3 / 4;
        margin-inline: auto;
        border-radius: 20px;
        height: max(80px, 30vh);

        /* border: 4px var(--fundo-0) solid; */
        box-shadow: 4px 4px 4px hsl(from var(--fundo-0) 0 0 8%);
        /* box-shadow: 4px 4px white; */
    }

    .conteiner {
        padding-block: 2rem;
        padding-inline: 3rem;
        background-color: var(--fundo-1);
        border-radius: 8px;

        &:last-child {
            border-radius: 8px 8px 16px 16px;
        }
        &:first-child {
            border-radius: 16px 16px 8px 8px;
        }
    }

    .sobre-mim {
        display: flex;
        align-items: center;
        column-gap: 1rem;

        @media screen and (width <= 850px) {
            flex-direction: column;
            row-gap: 1rem;

            & .infos .vulgo {
                text-align: center;
            }
        }
    }

    footer {
        display: grid;
        width: 100%;
        grid-template-columns: 1fr 1fr 1fr;
        /* justify-content: center; */
        margin-top: 3rem;
    }
    footer div {
        text-align: center;
    }

    .sociais a {
        display: grid;
        column-gap: 0.5rem;
        grid-template-columns: 1.5rem 1fr;
    }
    .sociais .links {
        margin-top: 0.5rem;
        display: flex;
        justify-content: center;
        column-gap: 2rem;
    }
    .wrap-cod-fonte {
        display: grid;
        padding-right: 1rem;
        place-content: end;
    }

    .wrap-cod-fonte a {
        color: var(--fundo-1);
    }

    a {
        text-decoration: none;
        color: white;
    }
    a:hover {
        text-decoration: underline;
    }

    ul {
        margin: 0;
        padding: 0;
    }

    .projetos {
        margin-top: 1rem;
    }

    .cartao {
        display: flex;
        width: 100%;
        align-items: center;
    }

    .cartao .conteudo {
        flex: 4;
    }

    .cartao > a {
        display: grid;
        place-content: center;

        color: var(--fundo-0);

        flex: 1;
        height: 3rem;
        border-radius: 20px;
        border-style: none;
        background-color: var(--ter);

        &:hover {
            box-shadow: 4px 4px 4px hsl(from var(--fundo-0) 0 0 8%);
        }
    }
</style>
