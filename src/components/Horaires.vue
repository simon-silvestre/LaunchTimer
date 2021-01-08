<template>
    <div class="horaires">
        <div class="card">
            <div class="haut">

            </div>
            <div class="bas">

            </div>
            <span class="nombre" :data-letters="chiffre">{{ chiffre }}</span>
        </div>
        <p class="name">{{ name }}</p>
    </div>
</template>

<script>
export default {
    props: {
        chiffre: Number,
        name: String
    }
}
</script>

<style lang="scss" scoped>
    .horaires {
        margin: 0 15px;
        .card {
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            width: 150px;
            height: 140px;
            color: hsl(345, 95%, 68%);
            box-shadow: 0px 8px 0px 0px #191b26;
            margin-top: 15px;

            &, .haut, .bas {
                border-radius: 8px;
            }

            .haut {
                position: absolute;
                top: 0;
                width: 100%;
                height: 70px;
                background-color: #2c2c45;
            }
            .bas {
                position: absolute;
                bottom: 0;
                width: 100%;
                height: 70px;
                background-color: #33364f;
            }
            .nombre {
                font-size: 80px;
                z-index: 1;
            }
            .nombre:after {
                content: attr(data-letters);
                z-index: 2;
                color: #d4526e;
                position: absolute;
                width: 100%;
                height: 100%;
                display: flex;
                justify-content: center;
                align-items: center;
                top: 0;
                left: 0;
                clip-path: polygon(0 0, 100% 0, 100% 50%, 0 50%);
            }
            &:before, &:after {
                content: '';
                position: absolute;
                width: 7px;
                height: 14px;
                background-color: #191b26;
                z-index: 1;
            }
            &:before {
                top: calc(50% - 7px);
                left: 0px;
                border-radius: 0 50px 50px 0;
            }
            &:after {
                top: calc(50% - 7px);
                right: 0px;
                border-radius: 50px 0 0 50px;
            }
        }
        .name {
            text-transform: uppercase;
            color: hsl(237, 18%, 59%);
            font-size: 14px;
            letter-spacing: 5px;
            margin: 0 auto;
            text-align: center;
            margin-top: 20px;
        }
    }
</style>