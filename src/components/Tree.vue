<script setup>
import ApexTree from 'apextree';
import { onMounted } from 'vue';

const data = {
        id: 'ms',
        data: {
          name: 'TUJUAN',
          text: 'Lorem ipsum dolor sit amet consectetur Lorem ipsum dolor sit amet consectetur',
          nameBgColor: '#3B68DD',
          borderColor: '#3B68DD',
        },
        options: {
          nodeBGColor: '#D1E1FF',
          nodeBGColorHover: '#D1E1FF',
        },
        children: [
          {
            id: 'mh',
            data: {
              name: 'INDIKATOR TUJUAN',
              text: 'Lorem ipsum dolor sit amet consectetur',
              nameBgColor: '#2B4BA7',
              borderColor: '#2B4BA7'
            },
            options: {
              nodeBGColor: '	#D1E1FF',
              nodeBGColorHover: '	#D1E1FF',
            },
            children: [
              {
                id: 'kb',
                data: {
                  name: 'SASARAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#57C58A',
                  borderColor: '#57C58A',
                },
                options: {
                  nodeBGColor: '#DEF8F6',
                  nodeBGColorHover: '#DEF8F6',
                },
                children: [
              {
                id: 'qw',
                data: {
                  name: 'INDIKATOR SASARAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#0F9D58',
                  borderColor: '#0F9D58',
                },
                options: {
                  nodeBGColor: '#D0F4F2',
                  nodeBGColorHover: '#D0F4F2',
                },
                children: [
              {
                id: 'er',
                data: {
                  name: 'PROGRAM',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#F04C43',
                  borderColor: '#F04C43',
                },
                options: {
                  nodeBGColor: '#F8DCE5',
                  nodeBGColorHover: '#F8DCE5',
                },
                children: [
              {
                id: 'ty',
                data: {
                  name: 'INDIKATOR PROGRAM',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#B8322C',
                  borderColor: '#B8322C',
                },
                options: {
                  nodeBGColor: '#F4CCD9',
                  nodeBGColorHover: '#F4CCD9',
                },
                children: [
              {
                id: 'ui',
                data: {
                  name: 'KEGIATAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#FFD04D',
                  borderColor: '#FFD04D',
                },
                options: {
                  nodeBGColor: '#F7E9DE',
                  nodeBGColorHover: '#F7E9DE',
                },
                children: [
              {
                id: 'op',
                data: {
                  name: 'INDIKATOR KEGIATAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#B59332',
                  borderColor: '#B59332',
                },
                options: {
                  nodeBGColor: '#F2DFD0',
                  nodeBGColorHover: '#F2DFD0',
                },
              },
            ]
              },
            ]
              },
            ]
              },
            ]
              },
            ]
              },
              {
                id: 'cr',
                data: {
                  name: 'SASARAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#57C58A',
                  borderColor: '#57C58A',
                },
                options: {
                  nodeBGColor: '#DEF8F6',
                  nodeBGColorHover: '#DEF8F6',
                },
                children: [
              {
                id: 'as',
                data: {
                  name: 'INDIKATOR SASARAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#0F9D58',
                  borderColor: '#0F9D58',
                },
                options: {
                  nodeBGColor: '#D0F4F2',
                  nodeBGColorHover: '#D0F4F2',
                },
                children: [
              {
                id: 'df',
                data: {
                  name: 'PROGRAM',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#F04C43',
                  borderColor: '#F04C43',
                },
                options: {
                  nodeBGColor: '#F8DCE5',
                  nodeBGColorHover: '#F8DCE5',
                },
                children: [
              {
                id: 'gh',
                data: {
                  name: 'INDIKATOR PROGRAM',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#B8322C',
                  borderColor: '#B8322C',
                },
                options: {
                  nodeBGColor: '#F4CCD9',
                  nodeBGColorHover: '#F4CCD9',
                },
                children: [
              {
                id: 'hj',
                data: {
                  name: 'KEGIATAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#FFD04D',
                  borderColor: '#FFD04D',
                },
                options: {
                  nodeBGColor: '#F7E9DE',
                  nodeBGColorHover: '#F7E9DE',
                },
                children: [
              {
                id: 'kl',
                data: {
                  name: 'INDIKATOR KEGIATAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#B59332',
                  borderColor: '#B59332',
                },
                options: {
                  nodeBGColor: '#F2DFD0',
                  nodeBGColorHover: '#F2DFD0',
                },
              },
            ]
              },
            ]
              },
            ]
              },
            ]
              },
            ]
              },
            ],
          },
          {
            id: 'cs',
            data: {
              name: 'INDIKATOR TUJUAN',
              text: 'Lorem ipsum dolor sit amet consectetur',
              nameBgColor: '#2B4BA7',
              borderColor: '#2B4BA7'
            },
            options: {
              nodeBGColor: '#D1E1FF',
              nodeBGColorHover: '	#D1E1FF',
            },
            children: [
              {
                id: 'zx',
                data: {
                  name: 'SASARAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#57C58A',
                  borderColor: '#57C58A',
                },
                options: {
                  nodeBGColor: '#DEF8F6',
                  nodeBGColorHover: '#DEF8F6',
                },
                children: [
              {
                id: 'cv',
                data: {
                  name: 'INDIKATOR SASARAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#0F9D58',
                  borderColor: '#0F9D58',
                },
                options: {
                  nodeBGColor: '#D0F4F2',
                  nodeBGColorHover: '#D0F4F2',
                },
                children: [
              {
                id: 'bn',
                data: {
                  name: 'PROGRAM',
                  text: 'Lorem ipsum dolor sit amet consectetur ',
                  nameBgColor: '#F04C43',
                  borderColor: '#F04C43',
                },
                options: {
                  nodeBGColor: '#F8DCE5',
                  nodeBGColorHover: '#F8DCE5',
                },
                children: [
              {
                id: 'nm',
                data: {
                  name: 'INDIKATOR PROGRAM',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#B8322C',
                  borderColor: '#B8322C',
                },
                options: {
                  nodeBGColor: '#F4CCD9',
                  nodeBGColorHover: '#F4CCD9',
                },
                children: [
              {
                id: 'za',
                data: {
                  name: 'KEGIATAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#FFD04D',
                  borderColor: '#FFD04D',
                },
                options: {
                  nodeBGColor: '#F7E9DE',
                  nodeBGColorHover: '#F7E9DE',
                },
                children: [
              {
                id: 'xs',
                data: {
                  name: 'INDIKATOR KEGIATAN',
                  text: 'Lorem ipsum dolor sit amet consectetur',
                  nameBgColor: '#B59332',
                  borderColor: '#B59332',
                },
                options: {
                  nodeBGColor: '#F2DFD0',
                  nodeBGColorHover: '#F2DFD0',
                },
              },
            ]
              },
            ]
              },
            ]
              },
            ]
              },
            ]
              },
            ]
          },
        ],
      };
      const options = {
            contentKey: 'data',
            width: 1000,
            height: 800,
            nodeWidth: 150,
            nodeHeight: 60,
            fontColor: '#fff',
            childrenSpacing: 30,
            siblingSpacing: 20,
            direction: 'top',
            enableExpandCollapse: true,
            nodeTemplate: (content) =>
              `<div style='
                display: flex;
                flex-direction: column;
                align-items: center;
                height: 100%;
                border: 1px solid ${content.borderColor};
                border-radius: 4.5px;'>
                  <div style="
                    font-weight: bold;
                    font-family: Arial;
                    font-size: 8px;
                    background-color: ${content.nameBgColor};
                    border-bottom: 1px solid ${content.borderColor};
                    width: 100%;
                    text-align: center;
                    padding-bottom: 5px;
                    padding-top: 5px;
                    border-radius: 4px 4px 0 0;">
                    ${content.name}
                  </div>
                  <p style="
                    height: auto;
                    display: flex;
                    justify-content: center;
                    font-family: Arial;
                    font-size: 8px;
                    text-align: center;
                    color: black;
                    padding: 5px 5px;
                    background-color: ${content.textBgColor};">
                    ${content.text}
                  </p>
              </div>`,
            canvasStyle: 'border: 1px solid black; background: #f6f6f6;',
            enableToolbar: true,
            initialZoom: 5, // Atur nilai zoom awal di sini (1.0 = skala 100%)
          };


onMounted(() => {
  const container = document.getElementById('svg-tree');
  if (container) {
    const tree = new ApexTree(container, options);
    tree.render(data);
  }
});
</script>

<template>
  <div>
    <div id="svg-tree"></div>
  </div>
</template>


<style scoped>
/* #svg-tree {
  width: 100%;
  height: 500px;
} */
</style>