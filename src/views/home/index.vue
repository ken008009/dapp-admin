<template>
    <PageView>
        <a-card class="cardCon" title="数据" :loading="loading">
            <a-row :gutter="0">
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>注册人数:</a> {{ data.totalUserR || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>激活总人数:</a> {{ data.totalUser || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>今日注册人数:</a> {{ data.todayUserR || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>今日激活人数:</a> {{ data.todayUser || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>认购总数:</a> {{ data.buyTotal || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>今日认购总数:</a> {{ data.todayBuy || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>全网可提U:</a> {{ data.balanceUsdt || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>今日静态:</a> {{ data.todayOne || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>今日动态:</a> {{ data.todayTwo || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>今日动静态:</a> {{ data.todayThree || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>总动静态累计:</a> {{ data.totalReward || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>今日提现:</a> {{ data.todayWithdraw || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>总提现:</a> {{ data.totalWithdraw || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
                <a-col :xs="12" :md="8" :lg="6" :xl="6">
                    <a-card-grid>
                        <a-icon type="team" />
                        <div>
                            <a>ispay总数:</a> {{ data.totalIspay || 0 }}
                        </div>
                    </a-card-grid>
                </a-col>
            </a-row>
        </a-card>
    </PageView>
</template>

<script type="text/jsx">
import Gai from '../../api/Gai'
export default {
    name: 'home',
    data() {
        return {
            loading: true,
            data: {},
        }
    },
    activated() {
        this.getList()
    },
    methods: {
        getList() {
            this.loading = true
            Gai.all().then(res => {
                this.data = res
                this.loading = false
            })
        },
    }
}
</script>

<style scoped lang="less">
.cardCon {
    /deep/ .ant-card-body {
        padding: 0 !important;
    }

    .ant-card-grid {
        padding: 24px 15px;
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: space-between;

        i {
            font-size: 20px;
            color: #ffffff;
            padding: 10px;
            border-radius: 8px;
            background: #1890ff;
        }
    }
}

.inputGroup {
    >div {
        margin: 20px;
    }
}
</style>