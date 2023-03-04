<script lang="ts">
export default {
  data: () => ({
    tab: null,
    datas: {
      ex1: {
        title: "例1",
        input: "3 2\n10 20 30\n1 3\n",
        output: "40\n",
      },
      ex2: {
        title: "例2",
        input: "4 1\n1 1 1 100\n4\n",
        output: "100\n",
      },
      ex3: {
        title: "例3",
        input: "8 4\n22 75 26 45 72 81 47 29\n4 6 7 8\n",
        output: "202\n",
      },
    },
  }),
  methods: {
    main(_input: string) {
      console.log(_input);
    },
  },
};
</script>
<template>
  <v-container>
    <h1>A - Contest Result</h1>
    <v-row>
      <v-col>
        <v-card id="description">
          <template v-slot:text>
            <h2>問題</h2>
            N問の問題からなるコンテストが開催され、i(1≤i≤N) 問目の配点は A_i
            点でした。 <br />
            すぬけくんはこのコンテストに参加し、 B_1,B_2,…,B_M問目の M
            問を解きました。 すぬけくんの総得点を求めてください。<br />
            ただし、総得点とは解いた問題の配点の総和を意味するものとします。
            <h2>制約</h2>
            <ul>
              <li>1≤M≤N≤100</li>
              <li>1≤A_i≤100</li>
              <li>1≤B_1&lt;B_2&lt;…&lt;B_M≤N</li>
              <li>入力は全て整数</li>
            </ul>
            <h2>入力</h2>
            <code>
              N M <br />
              A_1​ A_2​ … A_N<br />
              B_1​ B_2​ … B_N <br />
            </code>
            <h2>出力</h2>
            答えを整数として出力せよ。
          </template>
        </v-card>
      </v-col>
      <v-col>
        <v-card id="playground">
          <v-tabs v-model="tab">
            <v-tab value="one">例1</v-tab>
            <v-tab value="two">例2</v-tab>
            <v-tab value="three">例3</v-tab>
          </v-tabs>
          <v-card-text>
            <v-window v-model="tab">
              <v-window-item value="one">
                <div id="input_output">
                  <div>
                    <code>
                      {{ datas.ex1.input }}
                    </code>
                  </div>
                  <div>
                    <code>
                      {{ datas.ex1.output }}
                    </code>
                  </div>
                </div>
                <v-btn variant="outlined" @click="main(datas.ex1.input)">
                  RUN
                </v-btn>
              </v-window-item>

              <v-window-item value="two">
                <div id="input_output">
                  <div>
                    <code>
                      {{ datas.ex2.input }}
                    </code>
                  </div>
                  <div>
                    <code>
                      {{ datas.ex2.output }}
                    </code>
                  </div>
                </div>
                <v-btn variant="outlined" @click="main(datas.ex2.input)">
                  RUN
                </v-btn>
              </v-window-item>

              <v-window-item value="three">
                <div id="input_output">
                  <div>
                    <code>
                      {{ datas.ex3.input }}
                    </code>
                  </div>
                  <div>
                    <code>
                      {{ datas.ex3.output }}
                    </code>
                  </div>
                </div>
                <v-btn variant="outlined" @click="main(datas.ex3.input)">
                  RUN
                </v-btn>
              </v-window-item>
            </v-window>
          </v-card-text>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<style scoped>
code {
  display: inline-block;
  padding: 0.1em 0.25em; /* 文字周りの余白 */
  color: #444; /* 文字色 */
  background-color: #e7edf3; /* 背景色 */
  border-radius: 3px; /* 角丸 */
  border: solid 1px #d6dde4; /* 枠線 */
}
</style>