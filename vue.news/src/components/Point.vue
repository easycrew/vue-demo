<template>
  <section class="point">
      <div class='question'>
        <div class="mask">
          <h2>热点城市房价会否持续疯涨？</h2>
          <p>610期</p>
          <div class="result">
            <div class="yes">
              <span class="view">正方</span>
              <span class="num"></span>
              <span class="ratio">75%</span>
            </div>
            <div class="no">
              <span>反方</span>
              <span class="num"></span>
              <span>25%</span>
            </div>
          </div>
          <a class="join" href="javascript: void(0)">进入专题></a>
        </div>
      </div>
      <div class="prev">
        <div v-for='p in points' class="list">
          <div class="mask">
            <span class="times">{{p.times}}</span>
            <h2>{{p.title}}</h2>
             <p>{{p.msg}}</p>
             <a class="join" href="javascript: void(0)"> > </a>
          </div>
        </div>
      </div>
  </section>
</template>

<script>
import { mapState } from 'vuex'
export default {
  name: 'point',
  computed: {
    ...mapState({
      points: state => state.PointStore.points
    })
  }
}
</script>

<style lang="stylus">
.point{
  color: #fff;
  background: #fff;
  .question{
    height: 180px;
    background: url(../assets/point/pointBg.jpg);
    background-size: 100% 100%;
    .mask{
      display: flex;
      justify-content: center;
      flex-direction: column;
      align-items: center;
      height: 100%;
      width: 100%;
      position: relative;
      background: rgba(0,0,0,0.6);
      h2{
        font-size: 20px;
        font-weight: bold;
      }
      p{
        font-size: 16px;
        margin: 10px 0;
      }
      .result{
        height: 100px;
        width: 80%;
        display: flex;
        justify-content: space-between;
        text-align: center;
        .yes{
          height: 50px;
          display: flex;
          flex-direction: column;
          justify-content: flex-end;
          align-items: flex-start;
          width: 75%;
          .num{
            display: inline-block;
            height: 5px;
            width: 100%;
            margin: 5px 0;
            background: #E94C3D;
          }
        }
        .no{
          width: 25%;
          height: 50px;
          display: flex;
          flex-direction: column;
          justify-content: flex-end;
          align-items: flex-end;
          .num{
            display: inline-block;
            height: 5px;
            width: 100%;
            margin: 5px 0;
            background: #058;
          }
        }
      }
      .join{
        color: #E94C3D;
        position: absolute;
        bottom: 10px;
        right: 10px;
      }
    }
  }
  .prev{
    padding: 10px;
    .list{
      height: 150px;
      width: 100%;
      margin-bottom: 10px;
      overflow: hidden;
      background: url(../assets/point/pointBg.jpg) no-repeat;
      background-size: 100%;
      .mask{
        display: flex;
        justify-content: center;
        flex-direction: column;
        align-items: center;
        height: 100%;
        width: 100%;
        background: rgba(0,0,0,0.6);
        position: relative;
        h2{
          font-size: 20px;
          font-weight: bold;
          width: 100%;
          text-align: center;
          padding: 0 20px;
          overflow: hidden;
          white-space: nowrap;
          text-overflow: ellipsis;
        }
        p{
          color: #eee;
          margin: 10px 20px;
          line-height: 1.3;
          font-size: 13px;
          overflow: hidden;
          display: -webkit-box;
          word-break: break-all;
          -webkit-line-clamp: 2;
          text-overflow: ellipsis;
          -webkit-box-orient: vertical;
        }
        .times{
          position: absolute;
          left: 0;
          top: 0;
          color: #eee;
          display: inline-block;
          padding: 2px;
          font-size: 13px;
        }
        .join{
          position: absolute;
          right: 5px;
          bottom: 0;
          color: #eee;
          color: #E94C3D;
          display: inline-block;
          padding: 10px;
          font-size: 13px;
        }
      }
    }
  }
}
</style>
