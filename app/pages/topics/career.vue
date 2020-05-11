<template>
  <div>
    <v-timeline :dense="dense">
      <v-timeline-item
        v-for="career in careers"
        :key="career.title"
        :fill-dot="fillDot"
        :icon="career.icon"
      >
        <template v-slot:icon>
          <v-avatar v-if="avatar">
            <img src="http://i.pravatar.cc/64" />
          </v-avatar>
        </template>

        <v-card class="elevation-2" data-aos="zoom-in" data-aos-once="true">
          <v-card-title class="headline">
            {{ career.title }}
          </v-card-title>
          <v-card-subtitle>{{ career.term }}</v-card-subtitle>
          <v-card-text>
            {{ career.contents }}
          </v-card-text>
          <v-card-text class="font-weight-bold pb-0">経験</v-card-text>
          <div class="pb-3 pt-3">
            <v-chip
              v-for="(experience, i) in career.experiences"
              :key="`exp-${i}`"
              class="ml-2"
            >
              {{ experience }}
            </v-chip>
          </div>
        </v-card>
      </v-timeline-item>
    </v-timeline>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dense: true,
      fillDot: true,
      careers: [
        {
          title: "新卒入社",
          term: "2018/04",
          icon: "fas fa-running",
          contents:
            "静岡大学工学部数理システム工学科卒業後，株式会社アイヴィスに入社。B4では自動車間通信技術に関する研究をシミュレーションベースで行う。",
          experiences: ["Python3", "Linux"]
        },
        {
          title: "新人研修",
          term: "2018/04〜2018/6",
          icon: "fas fa-chalkboard-teacher",
          contents:
            "SQL, HTML, Java等を含んだ一般的な新人研修を会社から受ける。共同演習では，社内新人研修の利用を想定した答案採点システムをJava(JSP & Servelet)で作成。制作メンバーは6人",
          experiences: ["Java", "HTML", "SQL"]
        },
        {
          title: "運送業者の業務アプリ保守・追加機能開発",
          term: "2018/07〜2018/12",
          icon: "fas fa-truck",
          contents:
            "運送業者の業務アプリの保守現場に配属。アプリの要件変更に伴うシステムテスト(設計書修正, テスト証跡作成)，Excelファイル管理を行うための追加機能開発を基本設計から製造, リリースまで従事。プロジェクトメンバーは4〜6人。",
          process: ["設計", "製造", "テスト"],
          experiences: ["Java", "HTML", "CSS", "Javascript", "SQL"]
        },
        {
          title: "運送業者の業務アプリ新規開発",
          term: "2019/01〜2019/02",
          icon: "fas fa-file-invoice",
          contents:
            "保守案件で携わっていたアプリに連携予定の新規開発アプリの帳票出力機能を基本設計から単体テストまで担当。プロジェクトメンバーは10〜15人。",
          experiences: ["Java", "HTML", "CSS", "Javascript", "SQL"]
        },
        {
          title: "SaaS型データリポジトリ管理システムの開発補佐",
          term: "2018/04〜2018/6",
          icon: "fas fa-cloud-upload-alt",
          contents:
            "研究機関に向けたSaaS型リポジトリ管理システムのアジャイルでの新規開発案件に顧客現場に単身で常駐。キックスタート3年目で，アプリ開発は他ベンダーが請負。当初は開発機能のテストを担当する予定だったが，インフラ設計が追いついていないことを顧客と話し合い，インフラの設計・構築・検証を担当。裁量も多く，ベテランのシニアエンジニアの方とも仕事をこなせたため，この現場での経験が自分の中で特に色濃く根付いている。主に以下を経験。",
          topics: [
            "AWS上でのマネージドサービス(RDS, AES)を含むKubernetes環境のテスト構築(Cloudformation, eksctlでコードベースで作成)",
            "クローズドβ環境(KVM on OpenStackで約20サーバーが稼働し，その上でWebサーバー・関連ミドルウェアがdocker-composeで起動，Prometheus+Grafanaで監視)の構築・運用",
            "開発中アプリのElasticsearchバージョン上げ(v2→v6)のための互換性調査",
            "SonarQubeによる静的解析のためのPyLintルール・コーディング規約の策定(※運用方針も検討したが実運用には至らず)",
            "SSO用のShibboleth SPの構築・検証",
            "Kubernetesの調査，調査報告用のWiki作成",
            "クローズドβ環境のバージョン更新のためのAnsible Playbookの作成",
            "βテスト後の顧客ヒアリング，開発コスト等の検討"
          ]
        },
        {
          title: "新規開発(POC)",
          term: "2019/01〜2019/02",
          icon: "fas fa-video",
          contents:
            "PoCの画像認識による異常検知を目的としたIoTシステムの基盤(Jetson Nano,Jetson XavierをワーカーノードとしたkubeadmによるKubernetes環境)構築案件に携わる。その他Jetson上でのGPU利用のためのDockerfile作成，環境構築ドキュメント作成も担当。"
        }
      ]
    };
  }
};
</script>
