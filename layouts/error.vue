<template>
    <layout-wrapper>
        <layout-visual title="PAGE NOT FOUOND" :height="40" visual="visual-error" />
        <div class="w-full md:max-w-3xl mx-auto pt-20 pb-20 px-6 md:px-0">
            <div class="mb-20">
                <p class="text-center text-lg font-medium text-gray-900">
                    お探しのページは存在しません。
                </p>
            </div>
            <base-button name="トップページに戻る" link="/" />
        </div>
    </layout-wrapper>
</template>