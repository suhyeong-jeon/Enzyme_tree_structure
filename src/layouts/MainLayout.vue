<template>
  <q-tree
          :nodes="simple"
          node-key="label"
          selected-color="primary"
          v-model:selected="selected"
          v-on:click="[fnGetList(selected)]"
        />
</template>

<script>
import axios from 'axios'
import { ref } from 'vue'

export default {
  label: 'MainLayout',

  components: {

  },
  data () {
    return {
      enzymeNamelist: [],
      input_enzyme: '',
      sendData: '',
      chosen_enzyme: '',
      viewnum: '',
      eclist: [],
      enzymeslist: [],
      enzNum: '',
      remove_obj: '',
      obj: '',
      cmpenzNum: '',
      precmpenzNum: '',
      simple: [
        {
          label: '1. Oxidoreductases',
          idx: 0,

          children: [
            {
              label: '1.1 Acting on the CH-OH group of donors',
              idx: 11,
              children: [
                {
                  label: '1.1.1 With NAD+ or NADP+ as acceptor',
                  idx: 111,
                  children: [
                    { label: '1.1.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1111' },
                    { label: '1.1.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1112' },
                    { label: '1.1.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1113' },
                    { label: '1.1.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1114' },
                    { label: '1.1.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1115' },
                    { label: '1.1.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1116' },
                    { label: '1.1.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1118' },
                    { label: '1.1.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1119' },
                    { label: '1.1.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r11110' },
                    { label: '1.1.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r11111' },
                    { label: '1.1.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r11112' },
                    { label: '1.1.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r11114' },
                    { label: '1.1.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r11115' },
                    { label: '1.1.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r11116' },
                    { label: '1.1.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r11117' },
                    { label: '1.1.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r11118' },
                    { label: '1.1.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r11119' },
                    { label: '1.1.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r11120' },
                    { label: '1.1.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r11121' },
                    { label: '1.1.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r11122' },
                    { label: '1.1.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r11123' },
                    { label: '1.1.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r11124' },
                    { label: '1.1.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r11125' },
                    { label: '1.1.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r11126' },
                    { label: '1.1.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r11127' },
                    { label: '1.1.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r11128' },
                    { label: '1.1.1.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r11129' },
                    { label: '1.1.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r11130' },
                    { label: '1.1.1.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r11131' },
                    { label: '1.1.1.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r11133' },
                    { label: '1.1.1.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r11134' },
                    { label: '1.1.1.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r11135' },
                    { label: '1.1.1.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r11136' },
                    { label: '1.1.1.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r11137' },
                    { label: '1.1.1.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r11138' },
                    { label: '1.1.1.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r11139' },
                    { label: '1.1.1.40 ', children: [{ label: 'Select Enzyme' }], idx: 'r11140' },
                    { label: '1.1.1.41 ', children: [{ label: 'Select Enzyme' }], idx: 'r11141' },
                    { label: '1.1.1.42 ', children: [{ label: 'Select Enzyme' }], idx: 'r11142' },
                    { label: '1.1.1.44 ', children: [{ label: 'Select Enzyme' }], idx: 'r11144' },
                    { label: '1.1.1.45 ', children: [{ label: 'Select Enzyme' }], idx: 'r11145' },
                    { label: '1.1.1.47 ', children: [{ label: 'Select Enzyme' }], idx: 'r11147' },
                    { label: '1.1.1.48 ', children: [{ label: 'Select Enzyme' }], idx: 'r11148' },
                    { label: '1.1.1.49 ', children: [{ label: 'Select Enzyme' }], idx: 'r11149' },
                    { label: '1.1.1.50 ', children: [{ label: 'Select Enzyme' }], idx: 'r11150' },
                    { label: '1.1.1.51 ', children: [{ label: 'Select Enzyme' }], idx: 'r11151' },
                    { label: '1.1.1.52 ', children: [{ label: 'Select Enzyme' }], idx: 'r11152' },
                    { label: '1.1.1.53 ', children: [{ label: 'Select Enzyme' }], idx: 'r11153' },
                    { label: '1.1.1.54 ', children: [{ label: 'Select Enzyme' }], idx: 'r11154' },
                    { label: '1.1.1.56 ', children: [{ label: 'Select Enzyme' }], idx: 'r11156' },
                    { label: '1.1.1.57 ', children: [{ label: 'Select Enzyme' }], idx: 'r11157' },
                    { label: '1.1.1.58 ', children: [{ label: 'Select Enzyme' }], idx: 'r11158' },
                    { label: '1.1.1.60 ', children: [{ label: 'Select Enzyme' }], idx: 'r11160' },
                    { label: '1.1.1.61 ', children: [{ label: 'Select Enzyme' }], idx: 'r11161' },
                    { label: '1.1.1.62 ', children: [{ label: 'Select Enzyme' }], idx: 'r11162' },
                    { label: '1.1.1.63 ', children: [{ label: 'Select Enzyme' }], idx: 'r11163' },
                    { label: '1.1.1.64 ', children: [{ label: 'Select Enzyme' }], idx: 'r11164' },
                    { label: '1.1.1.65 ', children: [{ label: 'Select Enzyme' }], idx: 'r11165' },
                    { label: '1.1.1.66 ', children: [{ label: 'Select Enzyme' }], idx: 'r11166' },
                    { label: '1.1.1.67 ', children: [{ label: 'Select Enzyme' }], idx: 'r11167' },
                    { label: '1.1.1.69 ', children: [{ label: 'Select Enzyme' }], idx: 'r11169' },
                    { label: '1.1.1.71 ', children: [{ label: 'Select Enzyme' }], idx: 'r11171' },
                    { label: '1.1.1.72 ', children: [{ label: 'Select Enzyme' }], idx: 'r11172' },
                    { label: '1.1.1.73 ', children: [{ label: 'Select Enzyme' }], idx: 'r11173' },
                    { label: '1.1.1.76 ', children: [{ label: 'Select Enzyme' }], idx: 'r11176' },
                    { label: '1.1.1.77 ', children: [{ label: 'Select Enzyme' }], idx: 'r11177' },
                    { label: '1.1.1.79 ', children: [{ label: 'Select Enzyme' }], idx: 'r11179' },
                    { label: '1.1.1.80 ', children: [{ label: 'Select Enzyme' }], idx: 'r11180' },
                    { label: '1.1.1.81 ', children: [{ label: 'Select Enzyme' }], idx: 'r11181' },
                    { label: '1.1.1.82 ', children: [{ label: 'Select Enzyme' }], idx: 'r11182' },
                    { label: '1.1.1.83 ', children: [{ label: 'Select Enzyme' }], idx: 'r11183' },
                    { label: '1.1.1.85 ', children: [{ label: 'Select Enzyme' }], idx: 'r11185' },
                    { label: '1.1.1.86 ', children: [{ label: 'Select Enzyme' }], idx: 'r11186' },
                    { label: '1.1.1.87 ', children: [{ label: 'Select Enzyme' }], idx: 'r11187' },
                    { label: '1.1.1.88 ', children: [{ label: 'Select Enzyme' }], idx: 'r11188' },
                    { label: '1.1.1.90 ', children: [{ label: 'Select Enzyme' }], idx: 'r11190' },
                    { label: '1.1.1.91 ', children: [{ label: 'Select Enzyme' }], idx: 'r11191' },
                    { label: '1.1.1.93 ', children: [{ label: 'Select Enzyme' }], idx: 'r11193' },
                    { label: '1.1.1.94 ', children: [{ label: 'Select Enzyme' }], idx: 'r11194' },
                    { label: '1.1.1.95 ', children: [{ label: 'Select Enzyme' }], idx: 'r11195' },
                    { label: '1.1.1.96 ', children: [{ label: 'Select Enzyme' }], idx: 'r11196' },
                    { label: '1.1.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r111100' },
                    { label: '1.1.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r111101' },
                    { label: '1.1.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r111102' },
                    { label: '1.1.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r111103' },
                    { label: '1.1.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r111104' },
                    { label: '1.1.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r111105' },
                    { label: '1.1.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r111107' },
                    { label: '1.1.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r111108' },
                    { label: '1.1.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r111110' },
                    { label: '1.1.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r111112' },
                    { label: '1.1.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r111116' },
                    { label: '1.1.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r111117' },
                    { label: '1.1.1.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r111118' },
                    { label: '1.1.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r111119' },
                    { label: '1.1.1.120 ', children: [{ label: 'Select Enzyme' }], idx: 'r111120' },
                    { label: '1.1.1.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r111122' },
                    { label: '1.1.1.124 ', children: [{ label: 'Select Enzyme' }], idx: 'r111124' },
                    { label: '1.1.1.125 ', children: [{ label: 'Select Enzyme' }], idx: 'r111125' },
                    { label: '1.1.1.126 ', children: [{ label: 'Select Enzyme' }], idx: 'r111126' },
                    { label: '1.1.1.127 ', children: [{ label: 'Select Enzyme' }], idx: 'r111127' },
                    { label: '1.1.1.130 ', children: [{ label: 'Select Enzyme' }], idx: 'r111130' },
                    { label: '1.1.1.132 ', children: [{ label: 'Select Enzyme' }], idx: 'r111132' },
                    { label: '1.1.1.133 ', children: [{ label: 'Select Enzyme' }], idx: 'r111133' },
                    { label: '1.1.1.135 ', children: [{ label: 'Select Enzyme' }], idx: 'r111135' },
                    { label: '1.1.1.136 ', children: [{ label: 'Select Enzyme' }], idx: 'r111136' },
                    { label: '1.1.1.138 ', children: [{ label: 'Select Enzyme' }], idx: 'r111138' },
                    { label: '1.1.1.140 ', children: [{ label: 'Select Enzyme' }], idx: 'r111140' },
                    { label: '1.1.1.141 ', children: [{ label: 'Select Enzyme' }], idx: 'r111141' },
                    { label: '1.1.1.144 ', children: [{ label: 'Select Enzyme' }], idx: 'r111144' },
                    { label: '1.1.1.145 ', children: [{ label: 'Select Enzyme' }], idx: 'r111145' },
                    { label: '1.1.1.146 ', children: [{ label: 'Select Enzyme' }], idx: 'r111146' },
                    { label: '1.1.1.149 ', children: [{ label: 'Select Enzyme' }], idx: 'r111149' },
                    { label: '1.1.1.153 ', children: [{ label: 'Select Enzyme' }], idx: 'r111153' },
                    { label: '1.1.1.154 ', children: [{ label: 'Select Enzyme' }], idx: 'r111154' },
                    { label: '1.1.1.156 ', children: [{ label: 'Select Enzyme' }], idx: 'r111156' },
                    { label: '1.1.1.157 ', children: [{ label: 'Select Enzyme' }], idx: 'r111157' },
                    { label: '1.1.1.158 ', children: [{ label: 'Select Enzyme' }], idx: 'r111158' },
                    { label: '1.1.1.159 ', children: [{ label: 'Select Enzyme' }], idx: 'r111159' },
                    { label: '1.1.1.162 ', children: [{ label: 'Select Enzyme' }], idx: 'r111162' },
                    { label: '1.1.1.163 ', children: [{ label: 'Select Enzyme' }], idx: 'r111163' },
                    { label: '1.1.1.168 ', children: [{ label: 'Select Enzyme' }], idx: 'r111168' },
                    { label: '1.1.1.169 ', children: [{ label: 'Select Enzyme' }], idx: 'r111169' },
                    { label: '1.1.1.170 ', children: [{ label: 'Select Enzyme' }], idx: 'r111170' },
                    { label: '1.1.1.173 ', children: [{ label: 'Select Enzyme' }], idx: 'r111173' },
                    { label: '1.1.1.175 ', children: [{ label: 'Select Enzyme' }], idx: 'r111175' },
                    { label: '1.1.1.176 ', children: [{ label: 'Select Enzyme' }], idx: 'r111176' },
                    { label: '1.1.1.178 ', children: [{ label: 'Select Enzyme' }], idx: 'r111178' },
                    { label: '1.1.1.179 ', children: [{ label: 'Select Enzyme' }], idx: 'r111179' },
                    { label: '1.1.1.181 ', children: [{ label: 'Select Enzyme' }], idx: 'r111181' },
                    { label: '1.1.1.183 ', children: [{ label: 'Select Enzyme' }], idx: 'r111183' },
                    { label: '1.1.1.184 ', children: [{ label: 'Select Enzyme' }], idx: 'r111184' },
                    { label: '1.1.1.188 ', children: [{ label: 'Select Enzyme' }], idx: 'r111188' },
                    { label: '1.1.1.189 ', children: [{ label: 'Select Enzyme' }], idx: 'r111189' },
                    { label: '1.1.1.190 ', children: [{ label: 'Select Enzyme' }], idx: 'r111190' },
                    { label: '1.1.1.191 ', children: [{ label: 'Select Enzyme' }], idx: 'r111191' },
                    { label: '1.1.1.192 ', children: [{ label: 'Select Enzyme' }], idx: 'r111192' },
                    { label: '1.1.1.193 ', children: [{ label: 'Select Enzyme' }], idx: 'r111193' },
                    { label: '1.1.1.194 ', children: [{ label: 'Select Enzyme' }], idx: 'r111194' },
                    { label: '1.1.1.195 ', children: [{ label: 'Select Enzyme' }], idx: 'r111195' },
                    { label: '1.1.1.196 ', children: [{ label: 'Select Enzyme' }], idx: 'r111196' },
                    { label: '1.1.1.197 ', children: [{ label: 'Select Enzyme' }], idx: 'r111197' },
                    { label: '1.1.1.198 ', children: [{ label: 'Select Enzyme' }], idx: 'r111198' },
                    { label: '1.1.1.200 ', children: [{ label: 'Select Enzyme' }], idx: 'r111200' },
                    { label: '1.1.1.201 ', children: [{ label: 'Select Enzyme' }], idx: 'r111201' },
                    { label: '1.1.1.202 ', children: [{ label: 'Select Enzyme' }], idx: 'r111202' },
                    { label: '1.1.1.203 ', children: [{ label: 'Select Enzyme' }], idx: 'r111203' },
                    { label: '1.1.1.204 ', children: [{ label: 'Select Enzyme' }], idx: 'r111204' },
                    { label: '1.1.1.205 ', children: [{ label: 'Select Enzyme' }], idx: 'r111205' },
                    { label: '1.1.1.206 ', children: [{ label: 'Select Enzyme' }], idx: 'r111206' },
                    { label: '1.1.1.208 ', children: [{ label: 'Select Enzyme' }], idx: 'r111208' },
                    { label: '1.1.1.209 ', children: [{ label: 'Select Enzyme' }], idx: 'r111209' },
                    { label: '1.1.1.210 ', children: [{ label: 'Select Enzyme' }], idx: 'r111210' },
                    { label: '1.1.1.211 ', children: [{ label: 'Select Enzyme' }], idx: 'r111211' },
                    { label: '1.1.1.212 ', children: [{ label: 'Select Enzyme' }], idx: 'r111212' },
                    { label: '1.1.1.213 ', children: [{ label: 'Select Enzyme' }], idx: 'r111213' },
                    { label: '1.1.1.214 ', children: [{ label: 'Select Enzyme' }], idx: 'r111214' },
                    { label: '1.1.1.215 ', children: [{ label: 'Select Enzyme' }], idx: 'r111215' },
                    { label: '1.1.1.216 ', children: [{ label: 'Select Enzyme' }], idx: 'r111216' },
                    { label: '1.1.1.218 ', children: [{ label: 'Select Enzyme' }], idx: 'r111218' },
                    { label: '1.1.1.219 ', children: [{ label: 'Select Enzyme' }], idx: 'r111219' },
                    { label: '1.1.1.223 ', children: [{ label: 'Select Enzyme' }], idx: 'r111223' },
                    { label: '1.1.1.225 ', children: [{ label: 'Select Enzyme' }], idx: 'r111225' },
                    { label: '1.1.1.232 ', children: [{ label: 'Select Enzyme' }], idx: 'r111232' },
                    { label: '1.1.1.233 ', children: [{ label: 'Select Enzyme' }], idx: 'r111233' },
                    { label: '1.1.1.234 ', children: [{ label: 'Select Enzyme' }], idx: 'r111234' },
                    { label: '1.1.1.236 ', children: [{ label: 'Select Enzyme' }], idx: 'r111236' },
                    { label: '1.1.1.237 ', children: [{ label: 'Select Enzyme' }], idx: 'r111237' },
                    { label: '1.1.1.239 ', children: [{ label: 'Select Enzyme' }], idx: 'r111239' },
                    { label: '1.1.1.243 ', children: [{ label: 'Select Enzyme' }], idx: 'r111243' },
                    { label: '1.1.1.244 ', children: [{ label: 'Select Enzyme' }], idx: 'r111244' },
                    { label: '1.1.1.245 ', children: [{ label: 'Select Enzyme' }], idx: 'r111245' },
                    { label: '1.1.1.247 ', children: [{ label: 'Select Enzyme' }], idx: 'r111247' },
                    { label: '1.1.1.248 ', children: [{ label: 'Select Enzyme' }], idx: 'r111248' },
                    { label: '1.1.1.250 ', children: [{ label: 'Select Enzyme' }], idx: 'r111250' },
                    { label: '1.1.1.251 ', children: [{ label: 'Select Enzyme' }], idx: 'r111251' },
                    { label: '1.1.1.252 ', children: [{ label: 'Select Enzyme' }], idx: 'r111252' },
                    { label: '1.1.1.253 ', children: [{ label: 'Select Enzyme' }], idx: 'r111253' },
                    { label: '1.1.1.255 ', children: [{ label: 'Select Enzyme' }], idx: 'r111255' },
                    { label: '1.1.1.256 ', children: [{ label: 'Select Enzyme' }], idx: 'r111256' },
                    { label: '1.1.1.257 ', children: [{ label: 'Select Enzyme' }], idx: 'r111257' },
                    { label: '1.1.1.261 ', children: [{ label: 'Select Enzyme' }], idx: 'r111261' },
                    { label: '1.1.1.262 ', children: [{ label: 'Select Enzyme' }], idx: 'r111262' },
                    { label: '1.1.1.263 ', children: [{ label: 'Select Enzyme' }], idx: 'r111263' },
                    { label: '1.1.1.264 ', children: [{ label: 'Select Enzyme' }], idx: 'r111264' },
                    { label: '1.1.1.265 ', children: [{ label: 'Select Enzyme' }], idx: 'r111265' },
                    { label: '1.1.1.266 ', children: [{ label: 'Select Enzyme' }], idx: 'r111266' },
                    { label: '1.1.1.267 ', children: [{ label: 'Select Enzyme' }], idx: 'r111267' },
                    { label: '1.1.1.268 ', children: [{ label: 'Select Enzyme' }], idx: 'r111268' },
                    { label: '1.1.1.269 ', children: [{ label: 'Select Enzyme' }], idx: 'r111269' },
                    { label: '1.1.1.270 ', children: [{ label: 'Select Enzyme' }], idx: 'r111270' },
                    { label: '1.1.1.271 ', children: [{ label: 'Select Enzyme' }], idx: 'r111271' },
                    { label: '1.1.1.272 ', children: [{ label: 'Select Enzyme' }], idx: 'r111272' },
                    { label: '1.1.1.274 ', children: [{ label: 'Select Enzyme' }], idx: 'r111274' },
                    { label: '1.1.1.275 ', children: [{ label: 'Select Enzyme' }], idx: 'r111275' },
                    { label: '1.1.1.276 ', children: [{ label: 'Select Enzyme' }], idx: 'r111276' },
                    { label: '1.1.1.281 ', children: [{ label: 'Select Enzyme' }], idx: 'r111281' },
                    { label: '1.1.1.282 ', children: [{ label: 'Select Enzyme' }], idx: 'r111282' },
                    { label: '1.1.1.283 ', children: [{ label: 'Select Enzyme' }], idx: 'r111283' },
                    { label: '1.1.1.284 ', children: [{ label: 'Select Enzyme' }], idx: 'r111284' },
                    { label: '1.1.1.285 ', children: [{ label: 'Select Enzyme' }], idx: 'r111285' },
                    { label: '1.1.1.286 ', children: [{ label: 'Select Enzyme' }], idx: 'r111286' },
                    { label: '1.1.1.287 ', children: [{ label: 'Select Enzyme' }], idx: 'r111287' },
                    { label: '1.1.1.288 ', children: [{ label: 'Select Enzyme' }], idx: 'r111288' },
                    { label: '1.1.1.289 ', children: [{ label: 'Select Enzyme' }], idx: 'r111289' },
                    { label: '1.1.1.290 ', children: [{ label: 'Select Enzyme' }], idx: 'r111290' },
                    { label: '1.1.1.291 ', children: [{ label: 'Select Enzyme' }], idx: 'r111291' },
                    { label: '1.1.1.292 ', children: [{ label: 'Select Enzyme' }], idx: 'r111292' },
                    { label: '1.1.1.294 ', children: [{ label: 'Select Enzyme' }], idx: 'r111294' },
                    { label: '1.1.1.295 ', children: [{ label: 'Select Enzyme' }], idx: 'r111295' },
                    { label: '1.1.1.298 ', children: [{ label: 'Select Enzyme' }], idx: 'r111298' },
                    { label: '1.1.1.299 ', children: [{ label: 'Select Enzyme' }], idx: 'r111299' },
                    { label: '1.1.1.300 ', children: [{ label: 'Select Enzyme' }], idx: 'r111300' },
                    { label: '1.1.1.301 ', children: [{ label: 'Select Enzyme' }], idx: 'r111301' },
                    { label: '1.1.1.302 ', children: [{ label: 'Select Enzyme' }], idx: 'r111302' },
                    { label: '1.1.1.303 ', children: [{ label: 'Select Enzyme' }], idx: 'r111303' },
                    { label: '1.1.1.304 ', children: [{ label: 'Select Enzyme' }], idx: 'r111304' },
                    { label: '1.1.1.305 ', children: [{ label: 'Select Enzyme' }], idx: 'r111305' },
                    { label: '1.1.1.306 ', children: [{ label: 'Select Enzyme' }], idx: 'r111306' },
                    { label: '1.1.1.307 ', children: [{ label: 'Select Enzyme' }], idx: 'r111307' },
                    { label: '1.1.1.308 ', children: [{ label: 'Select Enzyme' }], idx: 'r111308' },
                    { label: '1.1.1.309 ', children: [{ label: 'Select Enzyme' }], idx: 'r111309' },
                    { label: '1.1.1.310 ', children: [{ label: 'Select Enzyme' }], idx: 'r111310' },
                    { label: '1.1.1.311 ', children: [{ label: 'Select Enzyme' }], idx: 'r111311' },
                    { label: '1.1.1.312 ', children: [{ label: 'Select Enzyme' }], idx: 'r111312' },
                    { label: '1.1.1.313 ', children: [{ label: 'Select Enzyme' }], idx: 'r111313' },
                    { label: '1.1.1.315 ', children: [{ label: 'Select Enzyme' }], idx: 'r111315' },
                    { label: '1.1.1.316 ', children: [{ label: 'Select Enzyme' }], idx: 'r111316' },
                    { label: '1.1.1.317 ', children: [{ label: 'Select Enzyme' }], idx: 'r111317' },
                    { label: '1.1.1.318 ', children: [{ label: 'Select Enzyme' }], idx: 'r111318' },
                    { label: '1.1.1.319 ', children: [{ label: 'Select Enzyme' }], idx: 'r111319' },
                    { label: '1.1.1.320 ', children: [{ label: 'Select Enzyme' }], idx: 'r111320' },
                    { label: '1.1.1.324 ', children: [{ label: 'Select Enzyme' }], idx: 'r111324' },
                    { label: '1.1.1.325 ', children: [{ label: 'Select Enzyme' }], idx: 'r111325' },
                    { label: '1.1.1.326 ', children: [{ label: 'Select Enzyme' }], idx: 'r111326' },
                    { label: '1.1.1.327 ', children: [{ label: 'Select Enzyme' }], idx: 'r111327' },
                    { label: '1.1.1.328 ', children: [{ label: 'Select Enzyme' }], idx: 'r111328' },
                    { label: '1.1.1.329 ', children: [{ label: 'Select Enzyme' }], idx: 'r111329' },
                    { label: '1.1.1.330 ', children: [{ label: 'Select Enzyme' }], idx: 'r111330' },
                    { label: '1.1.1.331 ', children: [{ label: 'Select Enzyme' }], idx: 'r111331' },
                    { label: '1.1.1.332 ', children: [{ label: 'Select Enzyme' }], idx: 'r111332' },
                    { label: '1.1.1.333 ', children: [{ label: 'Select Enzyme' }], idx: 'r111333' },
                    { label: '1.1.1.334 ', children: [{ label: 'Select Enzyme' }], idx: 'r111334' },
                    { label: '1.1.1.335 ', children: [{ label: 'Select Enzyme' }], idx: 'r111335' },
                    { label: '1.1.1.336 ', children: [{ label: 'Select Enzyme' }], idx: 'r111336' },
                    { label: '1.1.1.337 ', children: [{ label: 'Select Enzyme' }], idx: 'r111337' },
                    { label: '1.1.1.338 ', children: [{ label: 'Select Enzyme' }], idx: 'r111338' },
                    { label: '1.1.1.339 ', children: [{ label: 'Select Enzyme' }], idx: 'r111339' },
                    { label: '1.1.1.340 ', children: [{ label: 'Select Enzyme' }], idx: 'r111340' },
                    { label: '1.1.1.341 ', children: [{ label: 'Select Enzyme' }], idx: 'r111341' },
                    { label: '1.1.1.342 ', children: [{ label: 'Select Enzyme' }], idx: 'r111342' },
                    { label: '1.1.1.343 ', children: [{ label: 'Select Enzyme' }], idx: 'r111343' },
                    { label: '1.1.1.344 ', children: [{ label: 'Select Enzyme' }], idx: 'r111344' },
                    { label: '1.1.1.346 ', children: [{ label: 'Select Enzyme' }], idx: 'r111346' },
                    { label: '1.1.1.347 ', children: [{ label: 'Select Enzyme' }], idx: 'r111347' },
                    { label: '1.1.1.348 ', children: [{ label: 'Select Enzyme' }], idx: 'r111348' },
                    { label: '1.1.1.349 ', children: [{ label: 'Select Enzyme' }], idx: 'r111349' },
                    { label: '1.1.1.350 ', children: [{ label: 'Select Enzyme' }], idx: 'r111350' },
                    { label: '1.1.1.352 ', children: [{ label: 'Select Enzyme' }], idx: 'r111352' },
                    { label: '1.1.1.353 ', children: [{ label: 'Select Enzyme' }], idx: 'r111353' },
                    { label: '1.1.1.354 ', children: [{ label: 'Select Enzyme' }], idx: 'r111354' },
                    { label: '1.1.1.355 ', children: [{ label: 'Select Enzyme' }], idx: 'r111355' },
                    { label: '1.1.1.356 ', children: [{ label: 'Select Enzyme' }], idx: 'r111356' },
                    { label: '1.1.1.357 ', children: [{ label: 'Select Enzyme' }], idx: 'r111357' },
                    { label: '1.1.1.358 ', children: [{ label: 'Select Enzyme' }], idx: 'r111358' },
                    { label: '1.1.1.359 ', children: [{ label: 'Select Enzyme' }], idx: 'r111359' },
                    { label: '1.1.1.360 ', children: [{ label: 'Select Enzyme' }], idx: 'r111360' },
                    { label: '1.1.1.361 ', children: [{ label: 'Select Enzyme' }], idx: 'r111361' },
                    { label: '1.1.1.362 ', children: [{ label: 'Select Enzyme' }], idx: 'r111362' },
                    { label: '1.1.1.363 ', children: [{ label: 'Select Enzyme' }], idx: 'r111363' },
                    { label: '1.1.1.364 ', children: [{ label: 'Select Enzyme' }], idx: 'r111364' },
                    { label: '1.1.1.365 ', children: [{ label: 'Select Enzyme' }], idx: 'r111365' },
                    { label: '1.1.1.366 ', children: [{ label: 'Select Enzyme' }], idx: 'r111366' },
                    { label: '1.1.1.367 ', children: [{ label: 'Select Enzyme' }], idx: 'r111367' },
                    { label: '1.1.1.368 ', children: [{ label: 'Select Enzyme' }], idx: 'r111368' },
                    { label: '1.1.1.369 ', children: [{ label: 'Select Enzyme' }], idx: 'r111369' },
                    { label: '1.1.1.370 ', children: [{ label: 'Select Enzyme' }], idx: 'r111370' },
                    { label: '1.1.1.371 ', children: [{ label: 'Select Enzyme' }], idx: 'r111371' },
                    { label: '1.1.1.372 ', children: [{ label: 'Select Enzyme' }], idx: 'r111372' },
                    { label: '1.1.1.373 ', children: [{ label: 'Select Enzyme' }], idx: 'r111373' },
                    { label: '1.1.1.374 ', children: [{ label: 'Select Enzyme' }], idx: 'r111374' },
                    { label: '1.1.1.375 ', children: [{ label: 'Select Enzyme' }], idx: 'r111375' },
                    { label: '1.1.1.376 ', children: [{ label: 'Select Enzyme' }], idx: 'r111376' },
                    { label: '1.1.1.377 ', children: [{ label: 'Select Enzyme' }], idx: 'r111377' },
                    { label: '1.1.1.381 ', children: [{ label: 'Select Enzyme' }], idx: 'r111381' },
                    { label: '1.1.1.382 ', children: [{ label: 'Select Enzyme' }], idx: 'r111382' },
                    { label: '1.1.1.383 ', children: [{ label: 'Select Enzyme' }], idx: 'r111383' },
                    { label: '1.1.1.384 ', children: [{ label: 'Select Enzyme' }], idx: 'r111384' },
                    { label: '1.1.1.385 ', children: [{ label: 'Select Enzyme' }], idx: 'r111385' },
                    { label: '1.1.1.386 ', children: [{ label: 'Select Enzyme' }], idx: 'r111386' },
                    { label: '1.1.1.387 ', children: [{ label: 'Select Enzyme' }], idx: 'r111387' },
                    { label: '1.1.1.388 ', children: [{ label: 'Select Enzyme' }], idx: 'r111388' },
                    { label: '1.1.1.389 ', children: [{ label: 'Select Enzyme' }], idx: 'r111389' },
                    { label: '1.1.1.390 ', children: [{ label: 'Select Enzyme' }], idx: 'r111390' },
                    { label: '1.1.1.391 ', children: [{ label: 'Select Enzyme' }], idx: 'r111391' },
                    { label: '1.1.1.392 ', children: [{ label: 'Select Enzyme' }], idx: 'r111392' },
                    { label: '1.1.1.393 ', children: [{ label: 'Select Enzyme' }], idx: 'r111393' },
                    { label: '1.1.1.394 ', children: [{ label: 'Select Enzyme' }], idx: 'r111394' },
                    { label: '1.1.1.395 ', children: [{ label: 'Select Enzyme' }], idx: 'r111395' },
                    { label: '1.1.1.397 ', children: [{ label: 'Select Enzyme' }], idx: 'r111397' },
                    { label: '1.1.1.398 ', children: [{ label: 'Select Enzyme' }], idx: 'r111398' },
                    { label: '1.1.1.399 ', children: [{ label: 'Select Enzyme' }], idx: 'r111399' },
                    { label: '1.1.1.400 ', children: [{ label: 'Select Enzyme' }], idx: 'r111400' },
                    { label: '1.1.1.401 ', children: [{ label: 'Select Enzyme' }], idx: 'r111401' },
                    { label: '1.1.1.402 ', children: [{ label: 'Select Enzyme' }], idx: 'r111402' },
                    { label: '1.1.1.403 ', children: [{ label: 'Select Enzyme' }], idx: 'r111403' },
                    { label: '1.1.1.404 ', children: [{ label: 'Select Enzyme' }], idx: 'r111404' },
                    { label: '1.1.1.405 ', children: [{ label: 'Select Enzyme' }], idx: 'r111405' },
                    { label: '1.1.1.406 ', children: [{ label: 'Select Enzyme' }], idx: 'r111406' },
                    { label: '1.1.1.407 ', children: [{ label: 'Select Enzyme' }], idx: 'r111407' },
                    { label: '1.1.1.408 ', children: [{ label: 'Select Enzyme' }], idx: 'r111408' },
                    { label: '1.1.1.409 ', children: [{ label: 'Select Enzyme' }], idx: 'r111409' },
                    { label: '1.1.1.410 ', children: [{ label: 'Select Enzyme' }], idx: 'r111410' },
                    { label: '1.1.1.411 ', children: [{ label: 'Select Enzyme' }], idx: 'r111411' },
                    { label: '1.1.1.412 ', children: [{ label: 'Select Enzyme' }], idx: 'r111412' },
                    { label: '1.1.1.413 ', children: [{ label: 'Select Enzyme' }], idx: 'r111413' },
                    { label: '1.1.1.414 ', children: [{ label: 'Select Enzyme' }], idx: 'r111414' },
                    { label: '1.1.1.415 ', children: [{ label: 'Select Enzyme' }], idx: 'r111415' },
                    { label: '1.1.1.418 ', children: [{ label: 'Select Enzyme' }], idx: 'r111418' },
                    { label: '1.1.1.419 ', children: [{ label: 'Select Enzyme' }], idx: 'r111419' },
                    { label: '1.1.1.420 ', children: [{ label: 'Select Enzyme' }], idx: 'r111420' },
                    { label: '1.1.1.421 ', children: [{ label: 'Select Enzyme' }], idx: 'r111421' },
                    { label: '1.1.1.424 ', children: [{ label: 'Select Enzyme' }], idx: 'r111424' },
                    { label: '1.1.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r111-' },
                    { label: '1.1.1.n11 ', children: [{ label: 'Select Enzyme' }], idx: 'r111n11' },
                    { label: '1.1.1.n12 ', children: [{ label: 'Select Enzyme' }], idx: 'r111n12' },
                    { label: '1.1.1.n4 ', children: [{ label: 'Select Enzyme' }], idx: 'r111n4' },
                    { label: '1.1.1.n5 ', children: [{ label: 'Select Enzyme' }], idx: 'r111n5' }

                  ]
                },
                {
                  label: '1.1.2 With a cytochrome as acceptor',
                  idx: 112,
                  children: [
                    { label: '1.1.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r112-' },
                    { label: '1.1.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1123' },
                    { label: '1.1.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1124' },
                    { label: '1.1.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1126' },
                    { label: '1.1.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1127' },
                    { label: '1.1.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1128' },
                    { label: '1.1.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1129' }
                  ]
                },
                {
                  label: '1.1.3 With oxygen as acceptor',
                  idx: 113,
                  children: [
                    { label: '1.1.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131' },
                    { label: '1.1.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1132' },
                    { label: '1.1.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1134' },
                    { label: '1.1.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r11310' },
                    { label: '1.1.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r11312' },
                    { label: '1.1.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r11313' },
                    { label: '1.1.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r11315' },
                    { label: '1.1.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r11316' },
                    { label: '1.1.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r11317' },
                    { label: '1.1.3.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r11320' },
                    { label: '1.1.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r11321' },
                    { label: '1.1.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r11322' },
                    { label: '1.1.3.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r11325' },
                    { label: '1.1.3.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r11329' },
                    { label: '1.1.3.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r11337' },
                    { label: '1.1.3.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r11338' },
                    { label: '1.1.3.41 ', children: [{ label: 'Select Enzyme' }], idx: 'r11341' },
                    { label: '1.1.3.42 ', children: [{ label: 'Select Enzyme' }], idx: 'r11342' },
                    { label: '1.1.3.43 ', children: [{ label: 'Select Enzyme' }], idx: 'r11343' },
                    { label: '1.1.3.44 ', children: [{ label: 'Select Enzyme' }], idx: 'r11344' },
                    { label: '1.1.3.45 ', children: [{ label: 'Select Enzyme' }], idx: 'r11345' },
                    { label: '1.1.3.46 ', children: [{ label: 'Select Enzyme' }], idx: 'r11346' },
                    { label: '1.1.3.47 ', children: [{ label: 'Select Enzyme' }], idx: 'r11347' },
                    { label: '1.1.3.48 ', children: [{ label: 'Select Enzyme' }], idx: 'r11348' },
                    { label: '1.1.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r113-' }
                  ]
                },
                {
                  label: '1.1.4 With a disulfide as acceptor',
                  idx: 114,
                  children: [
                    { label: '1.1.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1142' }
                  ]
                },
                {
                  label: '1.1.5 With a quinone or similar compound as acceptor',
                  idx: 115,
                  children: [
                    { label: '1.1.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1152' },
                    { label: '1.1.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1153' },
                    { label: '1.1.5.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1154' },
                    { label: '1.1.5.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1155' },
                    { label: '1.1.5.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1158' },
                    { label: '1.1.5.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1159' },
                    { label: '1.1.5.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r11511' },
                    { label: '1.1.5.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r11512' },
                    { label: '1.1.5.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r11513' },
                    { label: '1.1.5.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r11514' },
                    { label: '1.1.5.- ', children: [{ label: 'Sekect Enzyme' }], idx: 'r115-' }
                  ]
                },
                {
                  label: '1.1.7 With an iron-sulfur protein as acceptor',
                  idx: 117,
                  children: [
                    { label: '1.1.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1171' }
                  ]
                },
                {
                  label: '1.1.9 With a copper protein as acceptor',
                  idx: 119,
                  children: [
                    { label: '1.1.9.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1191' }
                  ]
                },
                {
                  label: '1.1.98 With other, known, physiological acceptors',
                  idx: 1198,
                  children: [
                    { label: '1.1.98.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1198-' },
                    { label: '1.1.98.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11982' },
                    { label: '1.1.98.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11983' },
                    { label: '1.1.98.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r11986' },
                    { label: '1.1.98.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r11987' }
                  ]
                },
                {
                  label: '1.1.99 With unknown physiological acceptors',
                  idx: 1199,
                  children: [
                    { label: '1.1.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11991' },
                    { label: '1.1.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11992' },
                    { label: '1.1.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11993' },
                    { label: '1.1.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r11995' },
                    { label: '1.1.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r11996' },
                    { label: '1.1.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r11998' },
                    { label: '1.1.99.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r119914' },
                    { label: '1.1.99.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r119918' },
                    { label: '1.1.99.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r119922' },
                    { label: '1.1.99.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r119924' },
                    { label: '1.1.99.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r119928' },
                    { label: '1.1.99.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r119929' },
                    { label: '1.1.99.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r119930' },
                    { label: '1.1.99.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r119931' },
                    { label: '1.1.99.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r119932' },
                    { label: '1.1.99.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r119935' },
                    { label: '1.1.99.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r119936' },
                    { label: '1.1.99.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r119937' },
                    { label: '1.1.99.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r119938' },
                    { label: '1.1.99.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r119939' },
                    { label: '1.1.99.40 ', children: [{ label: 'Select Enzyme' }], idx: 'r119940' },
                    { label: '1.1.99.41 ', children: [{ label: 'Select Enzyme' }], idx: 'r119941' },
                    { label: '1.1.99.42 ', children: [{ label: 'Select Enzyme' }], idx: 'r119942' },
                    { label: '1.1.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1199-' }
                  ]
                }
              ]
            },
            {
              label: '1.2 Acting on the aldehyde or oxo group of donors',
              idx: 12,
              children: [
                {
                  label: '1.2.1 With NAD+ or NADP+ as acceptor',
                  idx: 121,
                  children: [
                    { label: '1.2.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1211' },
                    { label: '1.2.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1212' },
                    { label: '1.2.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1213' },
                    { label: '1.2.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r12110' },
                    { label: '1.2.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r12111' },
                    { label: '1.2.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r12112' },
                    { label: '1.2.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r12113' },
                    { label: '1.2.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r12116' },
                    { label: '1.2.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r12118' },
                    { label: '1.2.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r12119' },
                    { label: '1.2.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r12121' },
                    { label: '1.2.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r12122' },
                    { label: '1.2.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r12124' },
                    { label: '1.2.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r12126' },
                    { label: '1.2.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r12127' },
                    { label: '1.2.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r12128' },
                    { label: '1.2.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r12130' },
                    { label: '1.2.1.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r12131' },
                    { label: '1.2.1.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r12132' },
                    { label: '1.2.1.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r12136' },
                    { label: '1.2.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r121100' },
                    { label: '1.2.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r121101' },
                    { label: '1.2.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r121103' },
                    { label: '1.2.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r121106' },
                    { label: '1.2.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r121-' }
                  ]
                },
                {
                  label: '1.2.2 With a cytochrome as acceptor',
                  idx: 122,
                  children: [
                    { label: '1.2.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1222' }
                  ]
                },
                {
                  label: '1.2.3 With oxygen as acceptor',
                  idx: 123,
                  children: [
                    { label: '1.2.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1231' },
                    { label: '1.2.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1232' },
                    { label: '1.2.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1233' },
                    { label: '1.2.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1234' },
                    { label: '1.2.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1235' },
                    { label: '1.2.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1237' },
                    { label: '1.2.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r12314' },
                    { label: '1.2.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r12315' }
                  ]
                },
                {
                  label: '1.2.4 With a disulfide as acceptor',
                  idx: 124,
                  children: [
                    { label: '1.2.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1241' },
                    { label: '1.2.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1242' },
                    { label: '1.2.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1244' },
                    { label: '1.2.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r124-' }

                  ]
                },
                {
                  label: '1.2.5 With a quinone or similar compound as acceptor',
                  idx: 125,
                  children: [
                    { label: '1.2.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1251' },
                    { label: '1.2.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1252' },
                    { label: '1.2.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1253' }
                  ]
                },
                {
                  label: '1.2.7 With an iron-sulfur protein as acceptor',
                  idx: 127,
                  children: [
                    { label: '1.2.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1271' },
                    { label: '1.2.7.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1273' },
                    { label: '1.2.7.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1274' },
                    { label: '1.2.7.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1275' },
                    { label: '1.2.7.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1276' },
                    { label: '1.2.7.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1277' },
                    { label: '1.2.7.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1278' },
                    { label: '1.2.7.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r12710' },
                    { label: '1.2.7.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r12711' },
                    { label: '1.2.7.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r12712' },
                    { label: '1.2.7.- ', children: [{ label: 'Select Enzyme' }], idx: 'r127-' }
                  ]
                },
                {
                  label: '1.2.98. undefined',
                  idx: 1298,
                  children: [
                    { label: '1.2.98.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12981' }
                  ]
                },
                {
                  label: '1.2.99 With unknown physiological acceptors',
                  idx: 1299,
                  children: [
                    { label: '1.2.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r12992' },
                    { label: '1.2.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r12994' },
                    { label: '1.2.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r12995' },
                    { label: '1.2.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r12996' },
                    { label: '1.2.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r12997' },
                    { label: '1.2.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r12998' },
                    { label: '1.2.99.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r129910' },
                    { label: '1.2.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1299-' }
                  ]
                }
              ]
            },
            {
              label: '1.3 Acting on the CH-CH group of donors',
              idx: 13,
              children: [
                {
                  label: '1.3.1 With NAD+ or NADP+ as acceptor',
                  idx: 131,
                  children: [
                    { label: '1.3.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1311' },
                    { label: '1.3.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r13110' },
                    { label: '1.3.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r13112' },
                    { label: '1.3.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r131100' },
                    { label: '1.3.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r131101' },
                    { label: '1.3.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r131102' },
                    { label: '1.3.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r131103' },
                    { label: '1.3.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r131104' },
                    { label: '1.3.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r131105' },
                    { label: '1.3.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r131106' },
                    { label: '1.3.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r131107' },
                    { label: '1.3.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r131108' },
                    { label: '1.3.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r131110' },
                    { label: '1.3.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r131112' },
                    { label: '1.3.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r131113' },
                    { label: '1.3.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r131114' },
                    { label: '1.3.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r131115' },
                    { label: '1.3.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r131116' },
                    { label: '1.3.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r131119' },
                    { label: '1.3.1.120 ', children: [{ label: 'Select Enzyme' }], idx: 'r131120' },
                    { label: '1.3.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r131121' },
                    { label: '1.3.1.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r131122' },
                    { label: '1.3.1.123 ', children: [{ label: 'Select Enzyme' }], idx: 'r131123' },
                    { label: '1.3.1.124 ', children: [{ label: 'Select Enzyme' }], idx: 'r131124' },
                    { label: '1.3.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r131-' }
                  ]
                },
                {
                  label: '1.3.2 With a cytochrome as acceptor',
                  idx: 132,
                  children: [
                    { label: '1.3.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1323' },
                    { label: '1.3.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r132-' }
                  ]
                },
                {
                  label: '1.3.3 With oxygen as acceptor',
                  idx: 133,
                  children: [
                    { label: '1.3.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1331' },
                    { label: '1.3.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1333' },
                    { label: '1.3.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1334' },
                    { label: '1.3.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1335' },
                    { label: '1.3.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1336' },
                    { label: '1.3.3.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1338' },
                    { label: '1.3.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r13311' },
                    { label: '1.3.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r13312' },
                    { label: '1.3.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r13313' },
                    { label: '1.3.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r13314' },
                    { label: '1.3.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r13315' },
                    { label: '1.3.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r133-' }
                  ]
                },
                {
                  label: '1.3.4 With a disulfide as acceptor',
                  idx: 134,
                  children: [
                    { label: '1.3.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1341' }
                  ]
                },
                {
                  label: '1.3.5 With a quinone or related compound as acceptor',
                  idx: 135,
                  children: [
                    { label: '1.3.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1351' },
                    { label: '1.3.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1352' },
                    { label: '1.3.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1353' },
                    { label: '1.3.5.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1354' },
                    { label: '1.3.5.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1355' },
                    { label: '1.3.5.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1356' },
                    { label: '1.3.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r135-' }
                  ]
                },
                {
                  label: '1.3.7 With an iron-sulfur protein as acceptor',
                  idx: 137,
                  children: [
                    { label: '1.3.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1371' },
                    { label: '1.3.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1372' },
                    { label: '1.3.7.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1373' },
                    { label: '1.3.7.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1374' },
                    { label: '1.3.7.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1375' },
                    { label: '1.3.7.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1376' },
                    { label: '1.3.7.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1377' },
                    { label: '1.3.7.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1378' },
                    { label: '1.3.7.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r13711' },
                    { label: '1.3.7.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r13712' },
                    { label: '1.3.7.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r13715' }
                  ]
                },
                {
                  label: '1.3.8 With a flavin as acceptor',
                  idx: 138,
                  children: [
                    { label: '1.3.8.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1381' },
                    { label: '1.3.8.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1382' },
                    { label: '1.3.8.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1383' },
                    { label: '1.3.8.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1384' },
                    { label: '1.3.8.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1385' },
                    { label: '1.3.8.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1386' },
                    { label: '1.3.8.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1387' },
                    { label: '1.3.8.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1388' },
                    { label: '1.3.8.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1389' },
                    { label: '1.3.8.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r13810' },
                    { label: '1.3.8.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r13811' },
                    { label: '1.3.8.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r13812' },
                    { label: '1.3.8.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r13813' },
                    { label: '1.3.8.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r13814' },
                    { label: '1.3.8.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r13815' },
                    { label: '1.3.8.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r13816' },
                    { label: '1.3.8.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r13817' },
                    { label: '1.3.8.- ', children: [{ label: 'Select Enzyme' }], idx: 'r138-' }
                  ]
                },
                {
                  label: '1.3.98 With other, known, physiological acceptors',
                  idx: 1398,
                  children: [
                    { label: '1.3.98.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r13981' },
                    { label: '1.3.98.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r13983' },
                    { label: '1.3.98.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r13984' },
                    { label: '1.3.98.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r13985' },
                    { label: '1.3.98.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r13986' },
                    { label: '1.3.98.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r13987' },
                    { label: '1.3.98.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1398-' }
                  ]
                },
                {
                  label: '1.3.99 With unknown physiological acceptors',
                  idx: 1399,
                  children: [
                    { label: '1.3.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r13991' },
                    { label: '1.3.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r13992' },
                    { label: '1.3.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r13993' },
                    { label: '1.3.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r13994' },
                    { label: '1.3.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r13995' },
                    { label: '1.3.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r13997' },
                    { label: '1.3.99.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r139910' },
                    { label: '1.3.99.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r139911' },
                    { label: '1.3.99.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r139916' },
                    { label: '1.3.99.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r139917' },
                    { label: '1.3.99.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r139920' },
                    { label: '1.3.99.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r139923' },
                    { label: '1.3.99.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r139926' },
                    { label: '1.3.99.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r139927' },
                    { label: '1.3.99.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r139928' },
                    { label: '1.3.99.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r139929' },
                    { label: '1.3.99.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r139930' },
                    { label: '1.3.99.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r139931' },
                    { label: '1.3.99.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r139932' },
                    { label: '1.3.99.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r139933' },
                    { label: '1.3.99.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r139936' },
                    { label: '1.3.99.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r139937' },
                    { label: '1.3.99.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r139938' },
                    { label: '1.3.99.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r139939' },
                    { label: '1.3.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1399-' }
                  ]
                }
              ]
            },
            {
              label: '1.4 Acting on the CH-NH2 group of donors',
              idx: 14,
              children: [
                {
                  label: '1.4.1 With NAD+ or NADP+ as acceptor',
                  idx: 141,
                  children: [
                    { label: '1.4.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1411' },
                    { label: '1.4.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1412' },
                    { label: '1.4.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1413' },
                    { label: '1.4.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1414' },
                    { label: '1.4.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1419' },
                    { label: '1.4.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r14111' },
                    { label: '1.4.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r14112' },
                    { label: '1.4.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r14113' },
                    { label: '1.4.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r14114' },
                    { label: '1.4.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r14116' },
                    { label: '1.4.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r14117' },
                    { label: '1.4.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r14118' },
                    { label: '1.4.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r14119' },
                    { label: '1.4.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r14120' },
                    { label: '1.4.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r14121' },
                    { label: '1.4.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r14123' },
                    { label: '1.4.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r14124' },
                    { label: '1.4.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r14125' },
                    { label: '1.4.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r14126' },
                    { label: '1.4.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r141-' }
                  ]
                },
                {
                  label: '1.4.2 With a cytochrome as acceptor',
                  idx: 142,
                  children: [
                    { label: '1.4.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r142-' }
                  ]
                },
                {
                  label: '1.4.3 With oxygen as acceptor',
                  idx: 143,
                  children: [
                    { label: '1.4.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1431' },
                    { label: '1.4.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1432' },
                    { label: '1.4.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1433' },
                    { label: '1.4.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1434' },
                    { label: '1.4.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1435' },
                    { label: '1.4.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1436' },
                    { label: '1.4.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r14310' },
                    { label: '1.4.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r14311' },
                    { label: '1.4.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r14313' },
                    { label: '1.4.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r14314' },
                    { label: '1.4.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r14316' },
                    { label: '1.4.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r14319' },
                    { label: '1.4.3.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r14320' },
                    { label: '1.4.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r14321' },
                    { label: '1.4.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r14322' },
                    { label: '1.4.3.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r14323' },
                    { label: '1.4.3.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r14324' },
                    { label: '1.4.3.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r14325' },
                    { label: '1.4.3.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r14326' },
                    { label: '1.4.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r143-' }
                  ]
                },
                {
                  label: '1.4.4 With a disulfide as acceptor',
                  idx: 144,
                  children: [
                    { label: '1.4.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1442' }
                  ]
                },
                {
                  label: '1.4.5 With a quinone or other compound as acceptor',
                  idx: 145,
                  children: [
                    { label: '1.4.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1451' },
                    { label: '1.4.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r145-' }
                  ]
                },
                {
                  label: '1.4.7 With an iron-sulfur protein as acceptor',
                  idx: 147,
                  children: [
                    { label: '1.4.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1471' }
                  ]
                },
                {
                  label: '1.4.9 With a copper protein as acceptor',
                  idx: 149,
                  children: [
                    { label: '1.4.9.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1491' },
                    { label: '1.4.9.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1492' },
                    { label: '1.4.9.- ', children: [{ label: 'Select Enzyme' }], idx: 'r149-' }
                  ]
                },
                { label: '1.4.98. undefined', idx: 1498, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.4.99 With unknown physiological acceptors',
                  idx: 1499,
                  children: [
                    { label: '1.4.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r14993' },
                    { label: '1.4.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r14994' },
                    { label: '1.4.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r14995' },
                    { label: '1.4.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r14996' },
                    { label: '1.4.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1499-' }
                  ]
                }
              ]
            },
            {
              label: '1.5 Acting on the CH-NH group of donors',
              idx: 15,
              children: [
                {
                  label: '1.5.1 With NAD+ or NADP+ as acceptor',
                  idx: 151,
                  children: [
                    { label: '1.5.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1511' },
                    { label: '1.5.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1512' },
                    { label: '1.5.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1513' },
                    { label: '1.5.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r15110' },
                    { label: '1.5.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r15111' },
                    { label: '1.5.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r15112' },
                    { label: '1.5.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r15115' },
                    { label: '1.5.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r15116' },
                    { label: '1.5.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r15119' },
                    { label: '1.5.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r15120' },
                    { label: '1.5.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r15121' },
                    { label: '1.5.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r15123' },
                    { label: '1.5.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r15124' },
                    { label: '1.5.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r15125' },
                    { label: '1.5.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r15127' },
                    { label: '1.5.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r15128' },
                    { label: '1.5.1.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r15129' },
                    { label: '1.5.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r15130' },
                    { label: '1.5.1.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r15133' },
                    { label: '1.5.1.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r15134' },
                    { label: '1.5.1.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r15136' },
                    { label: '1.5.1.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r15137' },
                    { label: '1.5.1.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r15138' },
                    { label: '1.5.1.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r15139' },
                    { label: '1.5.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r151-' }
                  ]
                },
                {
                  label: '1.5.3 With oxygen as acceptor',
                  idx: 153,
                  children: [
                    { label: '1.5.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1531' },
                    { label: '1.5.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1535' },
                    { label: '1.5.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1536' },
                    { label: '1.5.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1537' },
                    { label: '1.5.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r15310' },
                    { label: '1.5.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r15311' },
                    { label: '1.5.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r15313' },
                    { label: '1.5.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r15314' },
                    { label: '1.5.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r15315' },
                    { label: '1.5.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r15316' },
                    { label: '1.5.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r15317' },
                    { label: '1.5.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r15318' },
                    { label: '1.5.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r15319' },
                    { label: '1.5.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r15321' },
                    { label: '1.5.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r15322' },
                    { label: '1.5.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r153-' }
                  ]
                },
                {
                  label: '1.5.4 With a disulfide as acceptor',
                  idx: 154,
                  children: [
                    { label: '1.5.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1541' }
                  ]
                },
                {
                  label: '1.5.5 With a quinone or similar compound as acceptor',
                  idx: 155,
                  children: [{ label: '1.5.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1551' },
                    { label: '1.5.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1552' },
                    { label: '1.5.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1553' },
                    { label: '1.5.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r155-' }
                  ]
                },
                {
                  label: '1.5.7 With an iron-sulfur protein as acceptor',
                  idx: 157,
                  children: [
                    { label: '1.5.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1572' }
                  ]
                },
                {
                  label: '1.5.8 With a flavin or flavoprotein as acceptor',
                  idx: 158,
                  children: [
                    { label: '1.5.8.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1581' },
                    { label: '1.5.8.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1582' },
                    { label: '1.5.8.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1583' },
                    { label: '1.5.8.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1584' },
                    { label: '1.5.8.- ', children: [{ label: 'Select Enzyme' }], idx: 'r158-' }
                  ]
                },
                {
                  label: '1.5.98 With other, known, physiological acceptors',
                  idx: 1598,
                  children: [
                    { label: '1.5.98.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r15981' },
                    { label: '1.5.98.2', children: [{ label: 'Select Enzyme' }], idx: 'r15982' }
                  ]
                },
                {
                  label: '1.5.99 With unknown physiological acceptors',
                  idx: 1599,
                  children: [
                    { label: '1.5.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r15996' },
                    { label: '1.5.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r15997' },
                    { label: '1.5.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r15998' },
                    { label: '1.5.99.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r15999' },
                    { label: '1.5.99.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r159911' },
                    { label: '1.5.99.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r159912' },
                    { label: '1.5.99.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r159913' },
                    { label: '1.5.99.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r159914' },
                    { label: '1.5.99.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r159915' },
                    { label: '1.5.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1599-' }
                  ]
                }
              ]
            },
            {
              label: '1.6 Acting on NADH or NADPH',
              idx: 16,
              children: [
                {
                  label: '1.6.1 With NAD+ or NADP+ as acceptor',
                  idx: 161,
                  children: [
                    { label: '1.6.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1611' },
                    { label: '1.6.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1612' },
                    { label: '1.6.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1614' }

                  ]
                },
                {
                  label: '1.6.2 With a heme protein as acceptor',
                  idx: 162,
                  children: [
                    { label: '1.6.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1622' },
                    { label: '1.6.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1624' },
                    { label: '1.6.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1626' },
                    { label: '1.6.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r162-' }
                  ]
                },
                {
                  label: '1.6.3 With oxygen as acceptor',
                  idx: 163,
                  children: [
                    { label: '1.6.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1631' },
                    { label: '1.6.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1632' },
                    { label: '1.6.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1634' },
                    { label: '1.6.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1635' },
                    { label: '1.6.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r163-' }
                  ]
                },
                {
                  label: '1.6.4 With a disulfide as acceptor (deleted sub-subclass)',
                  idx: 164,
                  children: [
                    { label: '1.6.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1642' },
                    { label: '1.6.4.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1645' },
                    { label: '1.6.4.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1648' }
                  ]
                },
                {
                  label: '1.6.5 With a quinone or similar compound as acceptor',
                  idx: 165,
                  children: [
                    { label: '1.6.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1652' },
                    { label: '1.6.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1653' },
                    { label: '1.6.5.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1654' },
                    { label: '1.6.5.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1655' },
                    { label: '1.6.5.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1656' },
                    { label: '1.6.5.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1657' },
                    { label: '1.6.5.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1659' },
                    { label: '1.6.5.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r16510' },
                    { label: '1.6.5.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r16511' },
                    { label: '1.6.5.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r16512' },
                    { label: '1.6.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r165-' }
                  ]
                },
                {
                  label: '1.6.6 With a nitrogenous group as acceptor',
                  idx: 166,
                  children: [
                    { label: '1.6.6.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1661' },
                    { label: '1.6.6.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1664' },
                    { label: '1.6.6.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1669' }

                  ]
                },
                { label: '1.6.7 With an iron-sulfur protein as acceptor (deleted sub-subclass)', idx: 167, children: [{ label: 'Select enzyme' }] },
                { label: '1.6.8 With a flavin as acceptor (deleted sub-subclass)', idx: 168, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.6.99 With unknown physiological acceptors',
                  idx: 1699,
                  children: [
                    { label: '1.6.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r16991' },
                    { label: '1.6.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r16992' },
                    { label: '1.6.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r16993' },
                    { label: '1.6.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r16995' },
                    { label: '1.6.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r16996' },
                    { label: '1.6.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r16997' },
                    { label: '1.6.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1699-' }
                  ]
                }
              ]
            },
            {
              label: '1.7 Acting on other nitrogenous compounds as donors',
              idx: 17,
              children: [
                {
                  label: '1.7.1 With NAD+ or NADP+ as acceptor',
                  idx: 171,
                  children: [
                    { label: '1.7.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1711' },
                    { label: '1.7.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1712' },
                    { label: '1.7.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1713' },
                    { label: '1.7.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1714' },
                    { label: '1.7.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1716' },
                    { label: '1.7.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1717' },
                    { label: '1.7.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r17113' },
                    { label: '1.7.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r17114' },
                    { label: '1.7.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r17115' },
                    { label: '1.7.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r17116' },
                    { label: '1.7.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r17117' },
                    { label: '1.7.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r171-' }
                  ]
                },
                {
                  label: '1.7.2 With a cytochrome as acceptor',
                  idx: 172,
                  children: [
                    { label: '1.7.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1721' },
                    { label: '1.7.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1722' },
                    { label: '1.7.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1723' },
                    { label: '1.7.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1724' },
                    { label: '1.7.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1725' },
                    { label: '1.7.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1726' },
                    { label: '1.7.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1727' },
                    { label: '1.7.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1728' },
                    { label: '1.7.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1729' }
                  ]
                },
                {
                  label: '1.7.3 With oxygen as acceptor',
                  idx: 173,
                  children: [
                    { label: '1.7.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1731' },
                    { label: '1.7.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1733' },
                    { label: '1.7.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1734' }
                  ]
                },
                {
                  label: '1.7.5 With a quinone or similar compound as acceptor',
                  idx: 175,
                  children: [
                    { label: '1.7.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1751' }
                  ]
                },
                {
                  label: '1.7.6 With a nitrogenous group as acceptor',
                  idx: 176,
                  children: [
                    { label: '1.7.6.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1761' }
                  ]
                },
                {
                  label: '1.7.7 With an iron-sulfur protein as acceptor',
                  idx: 177,
                  children: [
                    { label: '1.7.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1771' },
                    { label: '1.7.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1772' }

                  ]
                },
                { label: '1.7.9 With a copper protein as acceptor', idx: 179, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.7.99 With unknown physiological acceptors',
                  idx: 1799,
                  children: [
                    { label: '1.7.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r17991' },
                    { label: '1.7.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r17993' },
                    { label: '1.7.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r17994' },
                    { label: '1.7.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r17995' },
                    { label: '1.7.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r17996' },
                    { label: '1.7.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r17997' }
                  ]
                }
              ]
            },
            {
              label: '1.8 Acting on a sulfur group of donors',
              idx: 18,
              children: [
                {
                  label: '1.8.1 With NAD+ or NADP+ as acceptor',
                  idx: 181,
                  children: [
                    { label: '1.8.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1812' },
                    { label: '1.8.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1814' },
                    { label: '1.8.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1815' },
                    { label: '1.8.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1817' },
                    { label: '1.8.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1818' },
                    { label: '1.8.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1819' },
                    { label: '1.8.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r18112' },
                    { label: '1.8.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r18114' },
                    { label: '1.8.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r18115' },
                    { label: '1.8.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r18116' },
                    { label: '1.8.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r18118' },
                    { label: '1.8.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r18119' },
                    { label: '1.8.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r18120' },
                    { label: '1.8.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r181-' }

                  ]
                },
                {
                  label: '1.8.2 With a cytochrome as acceptor',
                  idx: 182,
                  children: [
                    { label: '1.8.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1821' },
                    { label: '1.8.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1822' },
                    { label: '1.8.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1823' },
                    { label: '1.8.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1824' }

                  ]
                },
                {
                  label: '1.8.3 With oxygen as acceptor',
                  idx: 183,
                  children: [
                    { label: '1.8.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1831' },
                    { label: '1.8.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1832' },
                    { label: '1.8.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1834' },
                    { label: '1.8.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1835' },
                    { label: '1.8.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1836' },
                    { label: '1.8.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1837' },
                    { label: '1.8.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r183-' }
                  ]
                },
                {
                  label: '1.8.4 With a disulfide as acceptor',
                  idx: 184,
                  children: [
                    { label: '1.8.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1842' },
                    { label: '1.8.4.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1846' },
                    { label: '1.8.4.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1847' },
                    { label: '1.8.4.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1848' },
                    { label: '1.8.4.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r1849' },
                    { label: '1.8.4.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r18410' },
                    { label: '1.8.4.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r18411' },
                    { label: '1.8.4.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r18412' },
                    { label: '1.8.4.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r18413' },
                    { label: '1.8.4.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r18414' },
                    { label: '1.8.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r184-' }

                  ]
                },
                {
                  label: '1.8.5 With a quinone or similar compound as acceptor',
                  idx: 185,
                  children: [
                    { label: '1.8.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1851' },
                    { label: '1.8.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1852' },
                    { label: '1.8.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1853' },
                    { label: '1.8.5.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r1854' },
                    { label: '1.8.5.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r1855' },
                    { label: '1.8.5.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r1856' },
                    { label: '1.8.5.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r1857' },
                    { label: '1.8.5.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r1858' },
                    { label: '1.8.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r185-' }
                  ]
                },
                { label: '1.8.6 With a nitrogenous group as acceptor (deleted sub-subclass)', idx: 186, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.8.7 With an iron-sulfur protein as acceptor',
                  idx: 187,
                  children: [
                    { label: '1.8.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1871' },
                    { label: '1.8.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1872' },
                    { label: '1.8.7.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r1873' }
                  ]
                },
                {
                  label: '1.8.98 With other, known, physiological acceptors',
                  idx: 1898,
                  children: [
                    { label: '1.8.98.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r18981' },
                    { label: '1.8.98.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r18982' },
                    { label: '1.8.98.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r18983' },
                    { label: '1.8.98.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r18984' },
                    { label: '1.8.98.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r18985' },
                    { label: '1.8.98.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r18986' },
                    { label: '1.8.98.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r18987' },
                    { label: '1.8.98.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1898-' }
                  ]
                },
                {
                  label: '1.8.99 With unknown physiological acceptors',
                  idx: 1899,
                  children: [
                    { label: '1.8.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r18992' },
                    { label: '1.8.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r18993' },
                    { label: '1.8.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r18994' },
                    { label: '1.8.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r18995' },
                    { label: '1.8.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1899-' }
                  ]
                }

              ]
            },
            {
              label: '1.9 Acting on a heme group of donors',
              idx: 19,
              children: [
                {
                  label: '1.9.3 With oxygen as acceptor',
                  idx: 193,
                  children: [
                    { label: '1.9.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1931' },
                    { label: '1.9.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r1932' },
                    { label: '1.9.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r193-' }
                  ]
                },
                {
                  label: '1.9.6 With a nitrogenous group as acceptor',
                  idx: 196,
                  children: [
                    { label: '1.9.6.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r1961' }
                  ]
                },
                { label: '1.9.98 With other, known, physiological acceptors', idx: 1998, children: [{ label: 'Select enzyme' }] },
                { label: '1.9.99 With unknown physiological acceptors', idx: 1999, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '1.10 Acting on diphenols and related substances as donors',
              idx: 110,
              children: [
                { label: '1.10.1 With NAD+ or NADP+ as acceptor', idx: 1101, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.10.2 With a cytochrome as acceptor',
                  idx: 1102,
                  children: [
                    { label: '1.10.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11022' }
                  ]
                },
                {
                  label: '1.10.3 With oxygen as acceptor',
                  idx: 1103,
                  children: [
                    { label: '1.10.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11031' },
                    { label: '1.10.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11032' },
                    { label: '1.10.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11033' },
                    { label: '1.10.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r11034' },
                    { label: '1.10.3.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r11039' },
                    { label: '1.10.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r110310' },
                    { label: '1.10.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r110311' },
                    { label: '1.10.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r110315' },
                    { label: '1.10.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r110316' },
                    { label: '1.10.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1103-' }
                  ]
                },
                {
                  label: '1.10.5 With a quinone or related compound as acceptor',
                  idx: 1105,
                  children: [
                    { label: '1.10.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11051' }
                  ]
                },
                {
                  label: '1.10.9 With a copper protein as acceptor',
                  idx: 1109,
                  children: [
                    { label: '1.10.9.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11091' }
                  ]
                },
                {
                  label: '1.10.99 With unknown physiological acceptors',
                  idx: 11099,
                  children: [
                    { label: '1.10.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r110991' },
                    { label: '1.10.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r110992' },
                    { label: '1.10.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r110993' }
                  ]
                }
              ]
            },
            {
              label: '1.11 Acting on a peroxide as acceptor',
              idx: 111,
              children: [
                {
                  label: '1.11.1 Peroxidases',
                  idx: 1111,
                  children: [
                    { label: '1.11.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11111' },
                    { label: '1.11.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11112' },
                    { label: '1.11.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r11115' },
                    { label: '1.11.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r11116' },
                    { label: '1.11.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r111110' },
                    { label: '1.11.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r111111' },
                    { label: '1.11.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r111112' },
                    { label: '1.11.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r111113' },
                    { label: '1.11.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r111114' },
                    { label: '1.11.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r111115' },
                    { label: '1.11.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r111116' },
                    { label: '1.11.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r111117' },
                    { label: '1.11.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r111118' },
                    { label: '1.11.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r111119' },
                    { label: '1.11.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r111120' },
                    { label: '1.11.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r111121' },
                    { label: '1.11.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r111122' },
                    { label: '1.11.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r111123' },
                    { label: '1.11.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r111124' },
                    { label: '1.11.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r111125' },
                    { label: '1.11.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r111126' },
                    { label: '1.11.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r111127' },
                    { label: '1.11.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r111128' },
                    { label: '1.11.1.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r111129' },
                    { label: '1.11.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1111-' }
                  ]
                },
                {
                  label: '1.11.2 Peroxygenases',
                  idx: 1112,
                  children: [
                    { label: '1.11.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11121' },
                    { label: '1.11.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11122' },
                    { label: '1.11.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11123' },
                    { label: '1.11.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r11124' },
                    { label: '1.11.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r11125' },
                    { label: '1.11.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1112-' }
                  ]
                }
              ]
            },
            {
              label: '1.12 Acting on hydrogen as donor',
              idx: 112,
              children: [
                {
                  label: '1.12.1 With NAD+ or NADP+ as acceptor',
                  idx: 1121,
                  children: [
                    { label: '1.12.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11212' },
                    { label: '1.12.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11213' },
                    { label: '1.12.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r11214' },
                    { label: '1.12.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r11215' }
                  ]
                },
                {
                  label: '1.12.2 With a cytochrome as acceptor',
                  idx: 1122,
                  children: [
                    { label: '1.12.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11221' }
                  ]
                },
                {
                  label: '1.12.5 With a quinone or similar compound as acceptor',
                  idx: 1125,
                  children: [
                    { label: '1.12.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11251' }
                  ]
                },
                {
                  label: '1.12.7 With an iron-sulfur protein as acceptor',
                  idx: 1127,
                  children: [
                    { label: '1.12.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11272' }
                  ]
                },
                {
                  label: '1.12.98 With other, known, physiological acceptors',
                  idx: 11298,
                  children: [
                    { label: '1.12.98.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r112981' },
                    { label: '1.12.98.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r112982' },
                    { label: '1.12.98.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r112983' },
                    { label: '1.12.98.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r112984' }
                  ]
                },
                {
                  label: '1.12.99 With unknown physiological acceptors',
                  idx: 11299,
                  children: [
                    { label: '1.12.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r112996' },
                    { label: '1.12.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11299-' }
                  ]
                }
              ]
            },
            {
              label: '1.13 Acting on single donors with incorporation of molecular oxygen (oxygenases)',
              idx: 12,
              children: [
                { label: '1.13.1. undefined', idx: 1131, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.13.11 With incorporation of two atoms of oxygen',
                  idx: 11311,
                  children: [
                    { label: '1.13.11.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r113111' },
                    { label: '1.13.11.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r113112' },
                    { label: '1.13.11.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r113113' },
                    { label: '1.13.11.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r113114' },
                    { label: '1.13.11.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131111' },
                    { label: '1.13.11.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131112' },
                    { label: '1.13.11.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131113' },
                    { label: '1.13.11.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131115' },
                    { label: '1.13.11.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131116' },
                    { label: '1.13.11.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131118' },
                    { label: '1.13.11.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131119' },
                    { label: '1.13.11.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131120' },
                    { label: '1.13.11.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131124' },
                    { label: '1.13.11.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131125' },
                    { label: '1.13.11.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131127' },
                    { label: '1.13.11.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131129' },
                    { label: '1.13.11.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131131' },
                    { label: '1.13.11.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131132' },
                    { label: '1.13.11.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131133' },
                    { label: '1.13.11.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131134' },
                    { label: '1.13.11.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131137' },
                    { label: '1.13.11.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131138' },
                    { label: '1.13.11.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131139' },
                    { label: '1.13.11.40 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131140' },
                    { label: '1.13.11.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11311-' }
                  ]
                },
                {
                  label: '1.13.12 With incorporation of one atom of oxygen (internal monooxygenases or internal mixed-function oxidases)',
                  idx: 11312,
                  children: [
                    { label: '1.13.12.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r113122' },
                    { label: '1.13.12.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r113123' },
                    { label: '1.13.12.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r113124' },
                    { label: '1.13.12.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r113125' },
                    { label: '1.13.12.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r113126' },
                    { label: '1.13.12.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r113127' },
                    { label: '1.13.12.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r113129' },
                    { label: '1.13.12.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131213' },
                    { label: '1.13.12.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131215' },
                    { label: '1.13.12.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131216' },
                    { label: '1.13.12.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131218' },
                    { label: '1.13.12.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131219' },
                    { label: '1.13.12.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131220' },
                    { label: '1.13.12.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131221' },
                    { label: '1.13.12.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131222' },
                    { label: '1.13.12.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r1131223' },
                    { label: '1.13.12.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11312-' }
                  ]
                },
                {
                  label: '1.13.99 Miscellaneous',
                  idx: 11399,
                  children: [
                    { label: '1.13.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r113991' }
                  ]
                }
              ]
            },
            {
              label: '1.14 Acting on paired donors, with incorporation or reduction of molecular oxygen',
              idx: 13,
              children: [
                { label: '1.14.1 With NADH or NADPH as one donor (deleted sub-subclass)', idx: 1141, children: [{ label: 'Select enzyme' }] },
                { label: '1.14.2 With ascorbate as one donor (deleted sub-subclass)', idx: 1142, children: [{ label: 'Select enzyme' }] },
                { label: '1.14.3 With reduced pteridine as one donor (deleted sub-subclass)', idx: 1143, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.14.11 With 2-oxoglutarate as one donor, and incorporation of one atom of oxygen into each donor',
                  idx: 11411,
                  children: [
                    { label: '1.14.11.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114111' },
                    { label: '1.14.11.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r114112' },
                    { label: '1.14.11.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141111' },
                    { label: '1.14.11.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141113' },
                    { label: '1.14.11.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141115' },
                    { label: '1.14.11.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141116' },
                    { label: '1.14.11.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141117' },
                    { label: '1.14.11.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141118' },
                    { label: '1.14.11.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141119' },
                    { label: '1.14.11.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141120' },
                    { label: '1.14.11.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141121' },
                    { label: '1.14.11.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141124' },
                    { label: '1.14.11.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141125' },
                    { label: '1.14.11.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141126' },
                    { label: '1.14.11.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141127' },
                    { label: '1.14.11.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141128' },
                    { label: '1.14.11.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141129' },
                    { label: '1.14.11.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141130' },
                    { label: '1.14.11.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141131' },
                    { label: '1.14.11.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141132' },
                    { label: '1.14.11.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141133' },
                    { label: '1.14.11.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141134' },
                    { label: '1.14.11.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141135' },
                    { label: '1.14.11.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141136' },
                    { label: '1.14.11.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11411-' }
                  ]
                },
                {
                  label: '1.14.12 With NADH or NADPH as one donor, and incorporation of two atoms of oxygen into the other donor',
                  idx: 11412,
                  children: [
                    { label: '1.14.12.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114121' },
                    { label: '1.14.12.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r114123' },
                    { label: '1.14.12.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r114124' },
                    { label: '1.14.12.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r114127' },
                    { label: '1.14.12.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141210' },
                    { label: '1.14.12.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141211' },
                    { label: '1.14.12.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141212' },
                    { label: '1.14.12.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141213' },
                    { label: '1.14.12.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141214' },
                    { label: '1.14.12.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141215' },
                    { label: '1.14.12.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141217' },
                    { label: '1.14.12.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141218' },
                    { label: '1.14.12.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141219' },
                    { label: '1.14.12.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141221' },
                    { label: '1.14.12.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141222' },
                    { label: '1.14.12.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141224' },
                    { label: '1.14.12.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141225' },
                    { label: '1.14.12.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141226' },
                    { label: '1.14.12.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11412-' }
                  ]
                },
                {
                  label: '1.14.13 With NADH or NADPH as one donor, and incorporation of one atom of oxygen into the other donor',
                  idx: 11413,
                  children: [
                    { label: '1.14.13.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114131' },
                    { label: '1.14.13.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141310' },
                    { label: '1.14.13.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141311' },
                    { label: '1.14.13.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141315' },
                    { label: '1.14.13.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141316' },
                    { label: '1.14.13.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413101' },
                    { label: '1.14.13.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413105' },
                    { label: '1.14.13.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413107' },
                    { label: '1.14.13.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413111' },
                    { label: '1.14.13.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413113' },
                    { label: '1.14.13.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413114' },
                    { label: '1.14.13.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413122' },
                    { label: '1.14.13.127 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413127' },
                    { label: '1.14.13.128 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413128' },
                    { label: '1.14.13.130 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413130' },
                    { label: '1.14.13.131 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413131' },
                    { label: '1.14.13.142 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413142' },
                    { label: '1.14.13.146 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413146' },
                    { label: '1.14.13.147 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413147' },
                    { label: '1.14.13.148 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413148' },
                    { label: '1.14.13.149 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413149' },
                    { label: '1.14.13.151 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413151' },
                    { label: '1.14.13.154 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413154' },
                    { label: '1.14.13.157 ', children: [{ label: 'Select Enzyme' }], idx: 'r11413157' },
                    { label: '1.14.13.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11413-' }
                  ]
                },
                {
                  label: '1.14.14 With reduced flavin or flavoprotein as one donor, and incorporation of one atom of oxygen into the other donor',
                  idx: 11414,
                  children: [
                    { label: '1.14.14.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114141' },
                    { label: '1.14.14.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141410' },
                    { label: '1.14.14.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141411' },
                    { label: '1.14.14.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141412' },
                    { label: '1.14.14.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414102' },
                    { label: '1.14.14.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414103' },
                    { label: '1.14.14.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414105' },
                    { label: '1.14.14.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414106' },
                    { label: '1.14.14.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414107' },
                    { label: '1.14.14.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414108' },
                    { label: '1.14.14.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414109' },
                    { label: '1.14.14.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414111' },
                    { label: '1.14.14.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414112' },
                    { label: '1.14.14.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414113' },
                    { label: '1.14.14.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414114' },
                    { label: '1.14.14.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414115' },
                    { label: '1.14.14.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414116' },
                    { label: '1.14.14.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414117' },
                    { label: '1.14.14.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414118' },
                    { label: '1.14.14.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414119' },
                    { label: '1.14.14.120 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414120' },
                    { label: '1.14.14.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414121' },
                    { label: '1.14.14.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414122' },
                    { label: '1.14.14.123 ', children: [{ label: 'Select Enzyme' }], idx: 'r11414123' },
                    { label: '1.14.14.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11414-' }
                  ]
                },
                {
                  label: '1.14.15 With reduced iron-sulfur protein as one donor, and incorporation of one atom of oxygen into the other donor',
                  idx: 11415,
                  children: [
                    { label: '1.14.15.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114151' },
                    { label: '1.14.15.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r114153' },
                    { label: '1.14.15.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r114154' },
                    { label: '1.14.15.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r114155' },
                    { label: '1.14.15.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141511' },
                    { label: '1.14.15.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141513' },
                    { label: '1.14.15.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141514' },
                    { label: '1.14.15.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141515' },
                    { label: '1.14.15.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141516' },
                    { label: '1.14.15.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141517' },
                    { label: '1.14.15.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141518' },
                    { label: '1.14.15.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141521' },
                    { label: '1.14.15.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141522' },
                    { label: '1.14.15.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141523' },
                    { label: '1.14.15.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141524' },
                    { label: '1.14.15.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141528' },
                    { label: '1.14.15.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141529' },
                    { label: '1.14.15.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141530' },
                    { label: '1.14.15.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141531' },
                    { label: '1.14.15.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141532' },
                    { label: '1.14.15.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141533' },
                    { label: '1.14.15.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141534' },
                    { label: '1.14.15.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141535' },
                    { label: '1.14.15.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141539' },
                    { label: '1.14.15.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11415-' }
                  ]
                },
                {
                  label: '1.14.16 With reduced pteridine as one donor, and incorporation of one atom of oxygen into the other donor',
                  idx: 11416,
                  children: [
                    { label: '1.14.16.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114161' },
                    { label: '1.14.16.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r114162' },
                    { label: '1.14.16.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r114164' },
                    { label: '1.14.16.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r114165' },
                    { label: '1.14.16.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r114167' },
                    { label: '1.14.16.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11416-' }
                  ]
                },
                {
                  label: '1.14.17 With reduced ascorbate as one donor, and incorporation of one atom of oxygen into the other donor',
                  idx: 11417,
                  children: [
                    { label: '1.14.17.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114171' },
                    { label: '1.14.17.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r114173' },
                    { label: '1.14.17.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r114174' },
                    { label: '1.14.17.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11417-' }

                  ]
                },
                {
                  label: '1.14.18 With another compound as one donor, and incorporation of one atom of oxygen into the other donor',
                  idx: 11418,
                  children: [
                    { label: '1.14.18.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114181' },
                    { label: '1.14.18.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r114182' },
                    { label: '1.14.18.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r114183' },
                    { label: '1.14.18.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r114184' },
                    { label: '1.14.18.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r114185' },
                    { label: '1.14.18.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r114186' },
                    { label: '1.14.18.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r114187' },
                    { label: '1.14.18.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r114188' },
                    { label: '1.14.18.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r114189' },
                    { label: '1.14.18.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141810' },
                    { label: '1.14.18.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141811' },
                    { label: '1.14.18.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141812' },
                    { label: '1.14.18.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11418-' }
                  ]
                },
                {
                  label: '1.14.19 With oxidation of a pair of donors resulting in the reduction of O2 to two molecules of water',
                  idx: 11419,
                  children: [
                    { label: '1.14.19.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114191' },
                    { label: '1.14.19.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r114192' },
                    { label: '1.14.19.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r114193' },
                    { label: '1.14.19.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141910' },
                    { label: '1.14.19.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141911' },
                    { label: '1.14.19.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141912' },
                    { label: '1.14.19.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141913' },
                    { label: '1.14.19.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141914' },
                    { label: '1.14.19.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141915' },
                    { label: '1.14.19.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141916' },
                    { label: '1.14.19.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141917' },
                    { label: '1.14.19.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141918' },
                    { label: '1.14.19.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141919' },
                    { label: '1.14.19.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141920' },
                    { label: '1.14.19.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141921' },
                    { label: '1.14.19.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141922' },
                    { label: '1.14.19.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141923' },
                    { label: '1.14.19.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141925' },
                    { label: '1.14.19.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141926' },
                    { label: '1.14.19.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141929' },
                    { label: '1.14.19.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141930' },
                    { label: '1.14.19.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141931' },
                    { label: '1.14.19.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141933' },
                    { label: '1.14.19.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r1141934' },
                    { label: '1.14.19.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11419-' }
                  ]
                },
                {
                  label: '1.14.20 With 2-oxoglutarate as one donor, and the other dehydrogenated',
                  idx: 11420,
                  children: [
                    { label: '1.14.20.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114201' },
                    { label: '1.14.20.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r114203' },
                    { label: '1.14.20.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r114204' },
                    { label: '1.14.20.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r114205' },
                    { label: '1.14.20.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r114206' },
                    { label: '1.14.20.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r114207' },
                    { label: '1.14.20.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r114208' },
                    { label: '1.14.20.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r114209' },
                    { label: '1.14.20.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r1142010' },
                    { label: '1.14.20.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r1142011' },
                    { label: '1.14.20.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1142015' },
                    { label: '1.14.20.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11420-' }
                  ]
                },
                {
                  label: '1.14.21 With NADH or NADPH as one donor, and the other dehydrogenated',
                  idx: 11421,
                  children: [
                    { label: '1.14.21.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r114217' },
                    { label: '1.14.21.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r114219' }
                  ]
                },
                {
                  label: '1.14.99 Miscellaneous',
                  idx: 11499,
                  children: [
                    { label: '1.14.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r114991' },
                    { label: '1.14.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r114993' },
                    { label: '1.14.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r114996' },
                    { label: '1.14.99.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149910' },
                    { label: '1.14.99.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149915' },
                    { label: '1.14.99.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149922' },
                    { label: '1.14.99.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149929' },
                    { label: '1.14.99.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149938' },
                    { label: '1.14.99.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149939' },
                    { label: '1.14.99.44 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149944' },
                    { label: '1.14.99.46 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149946' },
                    { label: '1.14.99.47 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149947' },
                    { label: '1.14.99.48 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149948' },
                    { label: '1.14.99.50 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149950' },
                    { label: '1.14.99.51 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149951' },
                    { label: '1.14.99.53 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149953' },
                    { label: '1.14.99.54 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149954' },
                    { label: '1.14.99.56 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149956' },
                    { label: '1.14.99.57 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149957' },
                    { label: '1.14.99.58 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149958' },
                    { label: '1.14.99.59 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149959' },
                    { label: '1.14.99.60 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149960' },
                    { label: '1.14.99.61 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149961' },
                    { label: '1.14.99.62 ', children: [{ label: 'Select Enzyme' }], idx: 'r1149962' },
                    { label: '1.14.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r11499-' }
                  ]
                }
              ]
            },
            {
              label: '1.15 Acting on superoxide as acceptor',
              idx: 115,
              children: [
                {
                  label: '1.15.1 Acting on superoxide as acceptor (only sub-subclass identified to date)',
                  idx: 1151,
                  children: [
                    { label: '1.15.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11511' },
                    { label: '1.15.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11512' }
                  ]
                }
              ]
            },
            {
              label: '1.16 Oxidizing metal ions',
              idx: 116,
              children: [
                {
                  label: '1.16.1 With NAD+ or NADP+ as acceptor',
                  idx: 1161,
                  children: [
                    { label: '1.16.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11611' },
                    { label: '1.16.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11612' },
                    { label: '1.16.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r11616' },
                    { label: '1.16.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r11617' },
                    { label: '1.16.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r11618' },
                    { label: '1.16.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r11619' },
                    { label: '1.16.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r116110' },
                    { label: '1.16.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1161-' }
                  ]
                },
                {
                  label: '1.16.3 With oxygen as acceptor',
                  idx: 1163,
                  children: [
                    { label: '1.16.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11631' },
                    { label: '1.16.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11632' },
                    { label: '1.16.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1163-' }
                  ]
                },
                {
                  label: '1.16.5 With a quinone or similar compound as acceptor',
                  idx: 1165,
                  children: [
                    { label: '1.16.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11651' }
                  ]
                },
                { label: '1.16.8 With a flavin as acceptor', idx: 1168, children: [{ label: 'Select enzyme' }] },
                { label: '1.16.9 With a copper protein as acceptor', idx: 1169, children: [{ label: 'Select enzyme' }] },
                { label: '1.16.98 With other, known, physiological acceptors', idx: 11698, children: [{ label: 'Select enzyme' }] },
                { label: '1.16.99 With unknown physiological acceptors', idx: 11699, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '1.17 Acting on CH or CH2 groups',
              idx: 117,
              children: [
                {
                  label: '1.17.1 With NAD+ or NADP+ as acceptor',
                  idx: 1171,
                  children: [
                    { label: '1.17.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11712' },
                    { label: '1.17.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11713' },
                    { label: '1.17.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r11714' },
                    { label: '1.17.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r11715' },
                    { label: '1.17.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r11718' },
                    { label: '1.17.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r11719' },
                    { label: '1.17.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1171-' }

                  ]
                },
                {
                  label: '1.17.2 With a cytochrome as acceptor',
                  idx: 1172,
                  children: [
                    { label: '1.17.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11721' },
                    { label: '1.17.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11722' },
                    { label: '1.17.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11723' }
                  ]
                },
                {
                  label: '1.17.3 With oxygen as acceptor',
                  idx: 1173,
                  children: [
                    { label: '1.17.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11732' },
                    { label: '1.17.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1173-' }
                  ]
                },
                {
                  label: '1.17.4 With a disulfide as acceptor',
                  idx: 1174,
                  children: [
                    { label: '1.17.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11741' },
                    { label: '1.17.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11742' },
                    { label: '1.17.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r11744' },
                    { label: '1.17.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1174-' }
                  ]
                },
                {
                  label: '1.17.5 With a quinone or similar compound as acceptor',
                  idx: 1175,
                  children: [
                    { label: '1.17.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11752' },
                    { label: '1.17.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11753' }
                  ]
                },
                {
                  label: '1.17.7 With an iron-sulfur protein as acceptor',
                  idx: 1177,
                  children: [
                    { label: '1.17.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11771' },
                    { label: '1.17.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11772' },
                    { label: '1.17.7.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11773' },
                    { label: '1.17.7.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r11774' }
                  ]
                },
                {
                  label: '1.17.8 With a flavin as acceptor',
                  idx: 1178,
                  children: [
                    { label: '1.17.8.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11781' }
                  ]
                },
                {
                  label: '1.17.9. undefined',
                  idx: 1179,
                  children: [
                    { label: '1.17.9.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11791' }
                  ]
                },
                {
                  label: '1.17.98 With other, known, physiological acceptors',
                  idx: 11798,
                  children: [
                    { label: '1.17.98.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r117982' },
                    { label: '1.17.98.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r117984' }
                  ]
                },
                {
                  label: '1.17.99 With unknown physiological acceptors',
                  idx: 11799,
                  children: [
                    { label: '1.17.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r117991' },
                    { label: '1.17.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r117992' },
                    { label: '1.17.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r117993' },
                    { label: '1.17.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r117996' },
                    { label: '1.17.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r117997' },
                    { label: '1.17.99.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r117999' }

                  ]
                }
              ]
            },
            {
              label: '1.18 Acting on iron-sulfur proteins as donors',
              idx: 118,
              children: [
                {
                  label: '1.18.1 With NAD+ or NADP+ as acceptor',
                  idx: 1181,
                  children: [
                    { label: '1.18.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11811' },
                    { label: '1.18.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r11812' },
                    { label: '1.18.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r11813' },
                    { label: '1.18.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r11814' },
                    { label: '1.18.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r11815' },
                    { label: '1.18.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r11816' },
                    { label: '1.18.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r11817' },
                    { label: '1.18.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1181-' }
                  ]
                },
                { label: '1.18.2 With dinitrogen as acceptor (deleted sub-subclass)', idx: 1182, children: [{ label: 'Select enzyme' }] },
                { label: '1.18.3 With H+ as acceptor (deleted sub-subclass)', idx: 1183, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.18.6 With dinitrogen as acceptor',
                  idx: 1186,
                  children: [
                    { label: '1.18.6.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11861' }
                  ]
                },
                { label: '1.18.96 With other, known, acceptors (deleted sub-subclass)', idx: 11896, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.18.99 With H+ as acceptor (deleted sub-subclass)',
                  idx: 11899,
                  children: [
                    { label: '1.18.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r118991' }

                  ]
                }
              ]
            },
            {
              label: '1.19 Acting on reduced flavodoxin as donor',
              idx: 119,
              children: [
                {
                  label: '1.19.1 With NAD+ or NADP+ as acceptor',
                  idx: 1191,
                  children: [
                    { label: '1.19.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r11911' }
                  ]
                },
                { label: '1.19.6 With dinitrogen as acceptor', idx: 1196, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '1.20 Acting on phosphorus or arsenic in donors',
              idx: 120,
              children: [
                {
                  label: '1.20.1 With NAD+ or NADP+ as acceptor',
                  idx: 1201,
                  children: [
                    { label: '1.20.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12011' }
                  ]
                },
                { label: '1.20.2 With a cytochrome as acceptor', idx: 1202, children: [{ label: 'Select enzyme' }] },
                {
                  label: '1.20.4 With disulfide as acceptor',
                  idx: 1204,
                  children: [
                    { label: '1.20.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12041' },
                    { label: '1.20.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r12042' },
                    { label: '1.20.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r12043' },
                    { label: '1.20.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r12044' },
                    { label: '1.20.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1204-' }
                  ]
                },
                {
                  label: '1.20.9 With a copper protein as acceptor',
                  idx: 1209,
                  children: [
                    { label: '1.20.9.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12091' }

                  ]
                },
                {
                  label: '1.20.98 With other, known, physiological acceptors',
                  idx: 12098,
                  children: [
                    { label: '1.20.98.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r120981' }
                  ]
                },
                {
                  label: '1.20.99 With unknown physiological acceptors',
                  idx: 12099,
                  children: [
                    { label: '1.20.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r120991' }
                  ]
                }
              ]
            },
            {
              label: '1.21 Catalysing the reaction X-H + Y-H = X-Y',
              idx: 121,
              children: [
                {
                  label: '1.21.1. undefined',
                  idx: 1211,
                  children: [
                    { label: '1.21.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12111' },
                    { label: '1.21.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1211-' }
                  ]
                },
                {
                  label: '1.21.3 With oxygen as acceptor',
                  idx: 1213,
                  children: [
                    { label: '1.21.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12131' },
                    { label: '1.21.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r12133' },
                    { label: '1.21.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r12136' },
                    { label: '1.21.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r12137' },
                    { label: '1.21.3.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r12138' },
                    { label: '1.21.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1213-' }
                  ]
                },
                {
                  label: '1.21.4 With a disulfide as acceptor',
                  idx: 1214,
                  children: [
                    { label: '1.21.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12141' },
                    { label: '1.21.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r12142' },
                    { label: '1.21.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r12143' },
                    { label: '1.21.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r12144' },
                    { label: '1.21.4.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r12145' }
                  ]
                },
                {
                  label: '1.21.98 With other, known, physiological acceptors',
                  idx: 12198,
                  children: [
                    { label: '1.21.98.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r121981' },
                    { label: '1.21.98.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r121982' },
                    { label: '1.21.98.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r121983' },
                    { label: '1.21.98.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r121984' },
                    { label: '1.21.98.- ', children: [{ label: 'Select Enzyme' }], idx: 'r12198-' }
                  ]
                },
                {
                  label: '1.21.99 With unknown physiological acceptors',
                  idx: 12199,
                  children: [
                    { label: '1.21.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r121991' },
                    { label: '1.21.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r121993' },
                    { label: '1.21.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r121994' },
                    { label: '1.21.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r121995' },
                    { label: '1.21.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r12199-' }

                  ]
                }
              ]
            },
            {
              label: '1.22 Acting on halogen in donors',
              idx: 122,
              children: [
                {
                  label: '1.22.1 With NAD+ or NADP+ as acceptor',
                  idx: 1221,
                  children: [
                    { label: '1.22.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12211' }
                  ]
                }
              ]
            },
            {
              label: '1.23 Reducing C-O-C group as acceptor',
              idx: 123,
              children: [
                {
                  label: '1.23.1 With NADH or NADPH as donor',
                  idx: 1231,
                  children: [
                    { label: '1.23.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12311' },
                    { label: '1.23.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r12312' },
                    { label: '1.23.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r12313' },
                    { label: '1.23.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r12314' },
                    { label: '1.23.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1231-' }

                  ]
                },
                {
                  label: '1.23.5 With a quinone or similar compound as acceptor',
                  idx: 1235,
                  children: [
                    { label: '1.23.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r12351' }
                  ]
                }
              ]
            },
            {
              label: '1.97 Other oxidoreductases',
              idx: 197,
              children: [
                {
                  label: '1.97.1 Sole sub-subclass for oxidoreductases that do not belong in the other subclasses',
                  idx: 1971,
                  children: [
                    { label: '1.97.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r19711' },
                    { label: '1.97.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r19712' },
                    { label: '1.97.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r19714' },
                    { label: '1.97.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r19715' },
                    { label: '1.97.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r19718' },
                    { label: '1.97.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r19719' },
                    { label: '1.97.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r197111' },
                    { label: '1.97.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r197112' },
                    { label: '1.97.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r1971-' }
                  ]
                }
              ]
            },
            {
              label: '1.98 Enzymes using H2 as reductant (deleted subclass)',
              idx: 198,
              children: [
                { label: '1.98.1. undefined', idx: 1981, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '1.99 Other enzymes using O2 as oxidant (deleted subclass)',
              idx: 199,
              children: [
                { label: '1.99.1 Hydroxylases (now covered by EC 1.14)', idx: 1991, children: [{ label: 'Select enzyme' }] },
                { label: '1.99.2 Oxygenases (now covered by EC 1.13)', idx: 1992, children: [{ label: 'Select enzyme' }] }
              ]
            }
          ]
        },
        {
          label: '2. Transferases',
          idx: 2,
          children: [
            {
              label: '2.1 Transferring one-carbon groups',
              idx: 21,
              children: [
                {
                  label: '2.1.1 Methyltransferases',
                  idx: 211,
                  children: [
                    { label: '2.1.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2111' },
                    { label: '2.1.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r21110' },
                    { label: '2.1.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r21111' },
                    { label: '2.1.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r21112' },
                    { label: '2.1.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r211100' },
                    { label: '2.1.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r211101' },
                    { label: '2.1.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r211102' },
                    { label: '2.1.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r211103' },
                    { label: '2.1.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r211104' },
                    { label: '2.1.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r211106' },
                    { label: '2.1.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r211107' },
                    { label: '2.1.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r211109' },
                    { label: '2.1.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r211110' },
                    { label: '2.1.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r211111' },
                    { label: '2.1.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r211112' },
                    { label: '2.1.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r211113' },
                    { label: '2.1.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r211114' },
                    { label: '2.1.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r211115' },
                    { label: '2.1.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r211116' },
                    { label: '2.1.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r211117' },
                    { label: '2.1.1.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r211118' },
                    { label: '2.1.1.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r211122' },
                    { label: '2.1.1.125 ', children: [{ label: 'Select Enzyme' }], idx: 'r211125' },
                    { label: '2.1.1.126 ', children: [{ label: 'Select Enzyme' }], idx: 'r211126' },
                    { label: '2.1.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r211-' }
                  ]
                },
                {
                  label: '2.1.2 Hydroxymethyl-, formyl- and related transferases',
                  idx: 212,
                  children: [
                    { label: '2.1.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2121' },
                    { label: '2.1.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2122' },
                    { label: '2.1.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2123' },
                    { label: '2.1.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2125' },
                    { label: '2.1.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r2127' },
                    { label: '2.1.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r2128' },
                    { label: '2.1.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2129' },
                    { label: '2.1.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r21210' },
                    { label: '2.1.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r21211' },
                    { label: '2.1.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r21213' },
                    { label: '2.1.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r21214' },
                    { label: '2.1.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r212-' }
                  ]
                },
                {
                  label: '2.1.3 Carboxy- and carbamoyltransferases',
                  idx: 213,
                  children: [
                    { label: '2.1.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2131' },
                    { label: '2.1.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2132' },
                    { label: '2.1.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2133' },
                    { label: '2.1.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r2136' },
                    { label: '2.1.3.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2139' },
                    { label: '2.1.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r21310' },
                    { label: '2.1.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r21311' },
                    { label: '2.1.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r21312' },
                    { label: '2.1.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r21315' },
                    { label: '2.1.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r213-' }
                  ]
                },
                {
                  label: '2.1.4 Amidinotransferases',
                  idx: 214,
                  children: [
                    { label: '2.1.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2141' },
                    { label: '2.1.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2142' },
                    { label: '2.1.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2143' }
                  ]
                },
                {
                  label: '2.1.5 Methylenetransferases',
                  idx: 215,
                  children: [
                    { label: '2.1.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2151' }
                  ]
                }
              ]
            },
            {
              label: '2.2 Transferring aldehyde or ketonic groups',
              idx: 22,
              children: [
                {
                  label: '2.2.1 Transketolases and transaldolases',
                  idx: 221,
                  children: [
                    { label: '2.2.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2211' },
                    { label: '2.2.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2212' },
                    { label: '2.2.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2213' },
                    { label: '2.2.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2215' },
                    { label: '2.2.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r2216' },
                    { label: '2.2.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r2217' },
                    { label: '2.2.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r2218' },
                    { label: '2.2.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2219' },
                    { label: '2.2.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r22110' },
                    { label: '2.2.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r22111' },
                    { label: '2.2.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r22112' },
                    { label: '2.2.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r22113' }
                  ]
                }
              ]
            },
            {
              label: '2.3 Acyltransferases',
              idx: 23,
              children: [
                {
                  label: '2.3.1 Transferring groups other than aminoacyl groups',
                  idx: 231,
                  children: [
                    { label: '2.3.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2311' },
                    { label: '2.3.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r23112' },
                    { label: '2.3.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r23113' },
                    { label: '2.3.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r231101' },
                    { label: '2.3.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r231102' },
                    { label: '2.3.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r231103' },
                    { label: '2.3.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r231107' },
                    { label: '2.3.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r231108' },
                    { label: '2.3.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r231109' },
                    { label: '2.3.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r231110' },
                    { label: '2.3.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r231111' },
                    { label: '2.3.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r231116' },
                    { label: '2.3.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r231117' },
                    { label: '2.3.1.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r231118' },
                    { label: '2.3.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r231121' },
                    { label: '2.3.1.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r231122' },
                    { label: '2.3.1.128 ', children: [{ label: 'Select Enzyme' }], idx: 'r231128' },
                    { label: '2.3.1.129 ', children: [{ label: 'Select Enzyme' }], idx: 'r231129' },
                    { label: '2.3.1.133 ', children: [{ label: 'Select Enzyme' }], idx: 'r231133' },
                    { label: '2.3.1.135 ', children: [{ label: 'Select Enzyme' }], idx: 'r231135' },
                    { label: '2.3.1.136 ', children: [{ label: 'Select Enzyme' }], idx: 'r231136' },
                    { label: '2.3.1.137 ', children: [{ label: 'Select Enzyme' }], idx: 'r231137' },
                    { label: '2.3.1.140 ', children: [{ label: 'Select Enzyme' }], idx: 'r231140' },
                    { label: '2.3.1.144 ', children: [{ label: 'Select Enzyme' }], idx: 'r231144' },
                    { label: '2.3.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r231-' }

                  ]
                },
                {
                  label: '2.3.2 Aminoacyltransferases',
                  idx: 232,
                  children: [
                    { label: '2.3.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2322' },
                    { label: '2.3.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2323' },
                    { label: '2.3.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r23210' },
                    { label: '2.3.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r23211' },
                    { label: '2.3.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r23212' },
                    { label: '2.3.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r23213' },
                    { label: '2.3.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r23215' },
                    { label: '2.3.2.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r23216' },
                    { label: '2.3.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r23217' },
                    { label: '2.3.2.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r23218' },
                    { label: '2.3.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r23219' },
                    { label: '2.3.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r23220' },
                    { label: '2.3.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r23221' },
                    { label: '2.3.2.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r23222' },
                    { label: '2.3.2.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r23223' },
                    { label: '2.3.2.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r23224' },
                    { label: '2.3.2.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r23225' },
                    { label: '2.3.2.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r23226' },
                    { label: '2.3.2.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r23227' },
                    { label: '2.3.2.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r23228' },
                    { label: '2.3.2.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r23229' },
                    { label: '2.3.2.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r23230' },
                    { label: '2.3.2.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r23231' },
                    { label: '2.3.2.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r23232' },
                    { label: '2.3.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r232-' }
                  ]
                },
                {
                  label: '2.3.3 Acyl groups converted into alkyl groups on transfer',
                  idx: 233,
                  children: [
                    { label: '2.3.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2331' },
                    { label: '2.3.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2333' },
                    { label: '2.3.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2335' },
                    { label: '2.3.3.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r2338' },
                    { label: '2.3.3.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2339' },
                    { label: '2.3.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r23310' },
                    { label: '2.3.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r23313' },
                    { label: '2.3.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r23314' },
                    { label: '2.3.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r23315' },
                    { label: '2.3.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r23316' },
                    { label: '2.3.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r23317' },
                    { label: '2.3.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r23318' },
                    { label: '2.3.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r23319' },
                    { label: '2.3.3.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r23320' },
                    { label: '2.3.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r233-' }
                  ]
                }
              ]
            },
            {
              label: '2.4 Glycosyltransferases',
              idx: 24,
              children: [
                {
                  label: '2.4.1 Hexosyltransferases',
                  idx: 241,
                  children: [
                    { label: '2.4.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2411' },
                    { label: '2.4.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r24110' },
                    { label: '2.4.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r24111' },
                    { label: '2.4.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r24112' },
                    { label: '2.4.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r24113' },
                    { label: '2.4.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r241100' },
                    { label: '2.4.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r241101' },
                    { label: '2.4.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r241102' },
                    { label: '2.4.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r241109' },
                    { label: '2.4.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r241111' },
                    { label: '2.4.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r241115' },
                    { label: '2.4.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r241116' },
                    { label: '2.4.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r241117' },
                    { label: '2.4.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r241119' },
                    { label: '2.4.1.120 ', children: [{ label: 'Select Enzyme' }], idx: 'r241120' },
                    { label: '2.4.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r241121' },
                    { label: '2.4.1.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r241122' },
                    { label: '2.4.1.123 ', children: [{ label: 'Select Enzyme' }], idx: 'r241123' },
                    { label: '2.4.1.126 ', children: [{ label: 'Select Enzyme' }], idx: 'r241126' },
                    { label: '2.4.1.128 ', children: [{ label: 'Select Enzyme' }], idx: 'r241128' },
                    { label: '2.4.1.129 ', children: [{ label: 'Select Enzyme' }], idx: 'r241129' },
                    { label: '2.4.1.131 ', children: [{ label: 'Select Enzyme' }], idx: 'r241131' },
                    { label: '2.4.1.132 ', children: [{ label: 'Select Enzyme' }], idx: 'r241132' },
                    { label: '2.4.1.133 ', children: [{ label: 'Select Enzyme' }], idx: 'r241133' },
                    { label: '2.4.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r241-' }
                  ]
                },
                {
                  label: '2.4.2 Pentosyltransferases',
                  idx: 242,
                  children: [
                    { label: '2.4.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2421' },
                    { label: '2.4.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2422' },
                    { label: '2.4.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2423' },
                    { label: '2.4.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r24210' },
                    { label: '2.4.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r24211' },
                    { label: '2.4.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r24212' },
                    { label: '2.4.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r24214' },
                    { label: '2.4.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r24217' },
                    { label: '2.4.2.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r24218' },
                    { label: '2.4.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r24219' },
                    { label: '2.4.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r24221' },
                    { label: '2.4.2.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r24222' },
                    { label: '2.4.2.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r24224' },
                    { label: '2.4.2.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r24226' },
                    { label: '2.4.2.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r24227' },
                    { label: '2.4.2.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r24228' },
                    { label: '2.4.2.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r24229' },
                    { label: '2.4.2.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r24230' },
                    { label: '2.4.2.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r24231' },
                    { label: '2.4.2.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r24234' },
                    { label: '2.4.2.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r24236' },
                    { label: '2.4.2.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r24237' },
                    { label: '2.4.2.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r24238' },
                    { label: '2.4.2.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r24239' },
                    { label: '2.4.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r242-' }
                  ]
                },
                { label: '2.4.3 Sialyltransferases', idx: 243, children: [{ label: 'Select enzyme' }] },
                {
                  label: '2.4.99 Transferring other glycosyl groups',
                  idx: 2499,
                  children: [
                    { label: '2.4.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r24991' },
                    { label: '2.4.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r24992' },
                    { label: '2.4.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r24993' },
                    { label: '2.4.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r24994' },
                    { label: '2.4.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r24996' },
                    { label: '2.4.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r24997' },
                    { label: '2.4.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r24998' },
                    { label: '2.4.99.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r24999' },
                    { label: '2.4.99.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r249912' },
                    { label: '2.4.99.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r249913' },
                    { label: '2.4.99.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r249914' },
                    { label: '2.4.99.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r249915' },
                    { label: '2.4.99.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r249916' },
                    { label: '2.4.99.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r249917' },
                    { label: '2.4.99.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r249918' },
                    { label: '2.4.99.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r249919' },
                    { label: '2.4.99.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r249920' },
                    { label: '2.4.99.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r249921' },
                    { label: '2.4.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r2499-' }
                  ]
                }
              ]
            },
            {
              label: '2.5 Transferring alkyl or aryl groups, other than methyl groups',
              idx: 25,
              children: [
                {
                  label: '2.5.1 Transferring alkyl or aryl groups, other than methyl groups (only sub-subclass identified to date)',
                  idx: 251,
                  children: [
                    { label: '2.5.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2511' },
                    { label: '2.5.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r25110' },
                    { label: '2.5.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r25111' },
                    { label: '2.5.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r251100' },
                    { label: '2.5.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r251101' },
                    { label: '2.5.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r251103' },
                    { label: '2.5.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r251104' },
                    { label: '2.5.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r251105' },
                    { label: '2.5.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r251106' },
                    { label: '2.5.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r251107' },
                    { label: '2.5.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r251108' },
                    { label: '2.5.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r251109' },
                    { label: '2.5.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r251110' },
                    { label: '2.5.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r251111' },
                    { label: '2.5.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r251112' },
                    { label: '2.5.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r251113' },
                    { label: '2.5.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r251114' },
                    { label: '2.5.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r251115' },
                    { label: '2.5.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r251116' },
                    { label: '2.5.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r251117' },
                    { label: '2.5.1.120 ', children: [{ label: 'Select Enzyme' }], idx: 'r251120' },
                    { label: '2.5.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r251121' },
                    { label: '2.5.1.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r251122' },
                    { label: '2.5.1.123 ', children: [{ label: 'Select Enzyme' }], idx: 'r251123' },
                    { label: '2.5.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r251-' }
                  ]
                }
              ]
            },
            {
              label: '2.6 Transferring nitrogenous groups',
              idx: 26,
              children: [
                {
                  label: '2.6.1 Transaminases',
                  idx: 261,
                  children: [
                    { label: '2.6.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2611' },
                    { label: '2.6.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r26111' },
                    { label: '2.6.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r26113' },
                    { label: '2.6.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r26114' },
                    { label: '2.6.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r26115' },
                    { label: '2.6.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r26116' },
                    { label: '2.6.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r261100' },
                    { label: '2.6.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r261101' },
                    { label: '2.6.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r261102' },
                    { label: '2.6.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r261103' },
                    { label: '2.6.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r261104' },
                    { label: '2.6.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r261105' },
                    { label: '2.6.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r261106' },
                    { label: '2.6.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r261107' },
                    { label: '2.6.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r261108' },
                    { label: '2.6.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r261109' },
                    { label: '2.6.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r261110' },
                    { label: '2.6.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r261111' },
                    { label: '2.6.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r261112' },
                    { label: '2.6.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r261113' },
                    { label: '2.6.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r261114' },
                    { label: '2.6.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r261117' },
                    { label: '2.6.1.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r261118' },
                    { label: '2.6.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r261119' },
                    { label: '2.6.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r261-' }
                  ]
                },
                { label: '2.6.2 Amidinotransferases (deleted sub-subclass)', idx: 262, children: [{ label: 'Select enzyme' }] },
                { label: '2.6.3 Oximinotransferases', idx: 263, children: [{ label: 'Select enzyme' }] },
                {
                  label: '2.6.99 Transferring other nitrogenous groups',
                  idx: 2699,
                  children: [
                    { label: '2.6.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r26992' },
                    { label: '2.6.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r26993' },
                    { label: '2.6.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r26994' },
                    { label: '2.6.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r2699-' }
                  ]
                }
              ]
            },
            {
              label: '2.7 Transferring phosphorus-containing groups',
              idx: 27,
              children: [
                {
                  label: '2.7.1 Phosphotransferases with an alcohol group as acceptor',
                  idx: 271,
                  children: [
                    { label: '2.7.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2711' },
                    { label: '2.7.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r27111' },
                    { label: '2.7.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r27112' },
                    { label: '2.7.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r27114' },
                    { label: '2.7.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r271100' },
                    { label: '2.7.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r271101' },
                    { label: '2.7.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r271103' },
                    { label: '2.7.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r271105' },
                    { label: '2.7.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r271106' },
                    { label: '2.7.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r271107' },
                    { label: '2.7.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r271108' },
                    { label: '2.7.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r271112' },
                    { label: '2.7.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r271113' },
                    { label: '2.7.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r271115' },
                    { label: '2.7.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r271117' },
                    { label: '2.7.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r271119' },
                    { label: '2.7.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r271121' },
                    { label: '2.7.1.123 ', children: [{ label: 'Select Enzyme' }], idx: 'r271123' },
                    { label: '2.7.1.126 ', children: [{ label: 'Select Enzyme' }], idx: 'r271126' },
                    { label: '2.7.1.127 ', children: [{ label: 'Select Enzyme' }], idx: 'r271127' },
                    { label: '2.7.1.130 ', children: [{ label: 'Select Enzyme' }], idx: 'r271130' },
                    { label: '2.7.1.134 ', children: [{ label: 'Select Enzyme' }], idx: 'r271134' },
                    { label: '2.7.1.137 ', children: [{ label: 'Select Enzyme' }], idx: 'r271137' },
                    { label: '2.7.1.138 ', children: [{ label: 'Select Enzyme' }], idx: 'r271138' },
                    { label: '2.7.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r271-' }
                  ]
                },
                {
                  label: '2.7.2 Phosphotransferases with a carboxy group as acceptor',
                  idx: 272,
                  children: [
                    { label: '2.7.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2721' },
                    { label: '2.7.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2722' },
                    { label: '2.7.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2723' },
                    { label: '2.7.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r2724' },
                    { label: '2.7.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r2727' },
                    { label: '2.7.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r2728' },
                    { label: '2.7.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r27211' },
                    { label: '2.7.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r27212' },
                    { label: '2.7.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r27215' },
                    { label: '2.7.2.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r27216' },
                    { label: '2.7.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r27217' },
                    { label: '2.7.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r272-' }
                  ]
                },
                {
                  label: '2.7.3 Phosphotransferases with a nitrogenous group as acceptor',
                  idx: 273,
                  children: [
                    { label: '2.7.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2731' },
                    { label: '2.7.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2732' },
                    { label: '2.7.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2733' },
                    { label: '2.7.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r2734' },
                    { label: '2.7.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2735' },
                    { label: '2.7.3.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2739' },
                    { label: '2.7.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r27313' },
                    { label: '2.7.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r273-' }
                  ]
                },
                {
                  label: '2.7.4 Phosphotransferases with a phosphate group as acceptor',
                  idx: 274,
                  children: [
                    { label: '2.7.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2741' },
                    { label: '2.7.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2742' },
                    { label: '2.7.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2743' },
                    { label: '2.7.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r2744' },
                    { label: '2.7.4.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r2746' },
                    { label: '2.7.4.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r2747' },
                    { label: '2.7.4.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r2748' },
                    { label: '2.7.4.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2749' },
                    { label: '2.7.4.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r27410' },
                    { label: '2.7.4.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r27413' },
                    { label: '2.7.4.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r27414' },
                    { label: '2.7.4.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r27416' },
                    { label: '2.7.4.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r27421' },
                    { label: '2.7.4.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r27422' },
                    { label: '2.7.4.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r27423' },
                    { label: '2.7.4.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r27424' },
                    { label: '2.7.4.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r27425' },
                    { label: '2.7.4.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r27426' },
                    { label: '2.7.4.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r27427' },
                    { label: '2.7.4.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r27428' },
                    { label: '2.7.4.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r27429' },
                    { label: '2.7.4.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r27431' },
                    { label: '2.7.4.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r27433' },
                    { label: '2.7.4.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r27434' },
                    { label: '2.7.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r274-' }
                  ]
                },
                {
                  label: '2.7.5 Phosphotransferases with regeneration of donors, apparently catalysing intramolecular transfers (deleted sub-subclass)',
                  idx: 275,
                  children: [
                    { label: '2.7.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2751' },
                    { label: '2.7.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2753' }

                  ]
                },
                {
                  label: '2.7.6 Diphosphotransferases',
                  idx: 276,
                  children: [
                    { label: '2.7.6.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2761' },
                    { label: '2.7.6.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2762' },
                    { label: '2.7.6.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2763' },
                    { label: '2.7.6.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2765' }

                  ]
                },
                {
                  label: '2.7.7 Nucleotidyltransferases',
                  idx: 277,
                  children: [
                    { label: '2.7.7.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2771' },
                    { label: '2.7.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2772' },
                    { label: '2.7.7.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2773' },
                    { label: '2.7.7.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r27710' },
                    { label: '2.7.7.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r27712' },
                    { label: '2.7.7.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r27713' },
                    { label: '2.7.7.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r27714' },
                    { label: '2.7.7.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r27715' },
                    { label: '2.7.7.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r27718' },
                    { label: '2.7.7.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r27719' },
                    { label: '2.7.7.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r27721' },
                    { label: '2.7.7.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r27723' },
                    { label: '2.7.7.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r27724' },
                    { label: '2.7.7.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r27725' },
                    { label: '2.7.7.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r27727' },
                    { label: '2.7.7.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r27730' },
                    { label: '2.7.7.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r27731' },
                    { label: '2.7.7.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r27733' },
                    { label: '2.7.7.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r277101' },
                    { label: '2.7.7.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r277102' },
                    { label: '2.7.7.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r277103' },
                    { label: '2.7.7.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r277104' },
                    { label: '2.7.7.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r277105' },
                    { label: '2.7.7.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r277106' },
                    { label: '2.7.7.- ', children: [{ label: 'Select Enzyme' }], idx: 'r277-' }
                  ]
                },
                {
                  label: '2.7.8 Transferases for other substituted phosphate groups',
                  idx: 278,
                  children: [
                    { label: '2.7.8.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2781' },
                    { label: '2.7.8.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2782' },
                    { label: '2.7.8.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r27811' },
                    { label: '2.7.8.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r27812' },
                    { label: '2.7.8.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r27813' },
                    { label: '2.7.8.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r27814' },
                    { label: '2.7.8.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r27815' },
                    { label: '2.7.8.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r27817' },
                    { label: '2.7.8.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r27820' },
                    { label: '2.7.8.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r27822' },
                    { label: '2.7.8.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r27823' },
                    { label: '2.7.8.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r27824' },
                    { label: '2.7.8.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r27826' },
                    { label: '2.7.8.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r27827' },
                    { label: '2.7.8.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r27828' },
                    { label: '2.7.8.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r27829' },
                    { label: '2.7.8.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r27831' },
                    { label: '2.7.8.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r27832' },
                    { label: '2.7.8.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r27833' },
                    { label: '2.7.8.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r27834' },
                    { label: '2.7.8.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r27835' },
                    { label: '2.7.8.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r27836' },
                    { label: '2.7.8.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r27837' },
                    { label: '2.7.8.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r27838' },
                    { label: '2.7.8.- ', children: [{ label: 'Select Enzyme' }], idx: 'r278-' }
                  ]
                },
                {
                  label: '2.7.9 Phosphotransferases with paired acceptors',
                  idx: 279,
                  children: [
                    { label: '2.7.9.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2791' },
                    { label: '2.7.9.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2792' },
                    { label: '2.7.9.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2793' },
                    { label: '2.7.9.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r2794' },
                    { label: '2.7.9.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2795' }
                  ]
                },
                {
                  label: '2.7.10 Protein-tyrosine kinases',
                  idx: 2710,
                  children: [
                    { label: '2.7.10.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r27101' },
                    { label: '2.7.10.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r27102' },
                    { label: '2.7.10.- ', children: [{ label: 'Select Enzyme' }], idx: 'r2710-' }
                  ]
                },
                {
                  label: '2.7.11 Protein-serine/threonine kinases',
                  idx: 2711,
                  children: [
                    { label: '2.7.11.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r27111' },
                    { label: '2.7.11.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r27112' },
                    { label: '2.7.11.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r271110' },
                    { label: '2.7.11.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r271111' },
                    { label: '2.7.11.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r271112' },
                    { label: '2.7.11.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r271113' },
                    { label: '2.7.11.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r271114' },
                    { label: '2.7.11.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r271115' },
                    { label: '2.7.11.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r271116' },
                    { label: '2.7.11.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r271117' },
                    { label: '2.7.11.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r271118' },
                    { label: '2.7.11.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r271119' },
                    { label: '2.7.11.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r271120' },
                    { label: '2.7.11.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r271121' },
                    { label: '2.7.11.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r271122' },
                    { label: '2.7.11.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r271123' },
                    { label: '2.7.11.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r271124' },
                    { label: '2.7.11.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r271125' },
                    { label: '2.7.11.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r271126' },
                    { label: '2.7.11.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r271127' },
                    { label: '2.7.11.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r271130' },
                    { label: '2.7.11.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r271131' },
                    { label: '2.7.11.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r271132' },
                    { label: '2.7.11.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r271133' },
                    { label: '2.7.11.- ', children: [{ label: 'Select Enzyme' }], idx: 'r2711-' }

                  ]
                },
                {
                  label: '2.7.12 Dual-specificity kinases (those acting on Ser/Thr and Tyr residues)',
                  idx: 2712,
                  children: [
                    { label: '2.7.12.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r27121' },
                    { label: '2.7.12.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r27122' }
                  ]
                },
                {
                  label: '2.7.13 Protein-histidine kinases',
                  idx: 2713,
                  children: [
                    { label: '2.7.13.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r27131' },
                    { label: '2.7.13.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r27133' },
                    { label: '2.7.13.- ', children: [{ label: 'Select Enzyme' }], idx: 'r2713-' }
                  ]
                },
                {
                  label: '2.7.14 Protein-arginine kinases',
                  idx: 2714,
                  children: [
                    { label: '2.7.14.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r27141' }
                  ]
                },
                {
                  label: '2.7.99 Other protein kinases',
                  idx: 2799,
                  children: [
                    { label: '2.7.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r27991' },
                    { label: '2.7.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r2799-' }
                  ]
                }
              ]
            },
            {
              label: '2.8 Transferring sulfur-containing groups',
              idx: 28,
              children: [
                {
                  label: '2.8.1 Sulfurtransferases',
                  idx: 281,
                  children: [
                    { label: '2.8.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2811' },
                    { label: '2.8.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2812' },
                    { label: '2.8.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r2814' },
                    { label: '2.8.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r2816' },
                    { label: '2.8.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r2817' },
                    { label: '2.8.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r2818' },
                    { label: '2.8.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2819' },
                    { label: '2.8.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r28110' },
                    { label: '2.8.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r28111' },
                    { label: '2.8.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r28112' },
                    { label: '2.8.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r28113' },
                    { label: '2.8.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r28114' },
                    { label: '2.8.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r28115' },
                    { label: '2.8.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r28116' },
                    { label: '2.8.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r281-' }
                  ]
                },
                {
                  label: '2.8.2 Sulfotransferases',
                  idx: 282,
                  children: [
                    { label: '2.8.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2821' },
                    { label: '2.8.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2822' },
                    { label: '2.8.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2823' },
                    { label: '2.8.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r2824' },
                    { label: '2.8.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2825' },
                    { label: '2.8.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r28211' },
                    { label: '2.8.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r28214' },
                    { label: '2.8.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r28217' },
                    { label: '2.8.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r28220' },
                    { label: '2.8.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r28221' },
                    { label: '2.8.2.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r28222' },
                    { label: '2.8.2.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r28223' },
                    { label: '2.8.2.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r28224' },
                    { label: '2.8.2.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r28225' },
                    { label: '2.8.2.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r28227' },
                    { label: '2.8.2.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r28229' },
                    { label: '2.8.2.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r28230' },
                    { label: '2.8.2.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r28233' },
                    { label: '2.8.2.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r28234' },
                    { label: '2.8.2.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r28235' },
                    { label: '2.8.2.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r28236' },
                    { label: '2.8.2.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r28237' },
                    { label: '2.8.2.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r28238' },
                    { label: '2.8.2.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r28239' },
                    { label: '2.8.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r282-' }
                  ]
                },
                {
                  label: '2.8.3 CoA-transferases',
                  idx: 283,
                  children: [
                    { label: '2.8.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2835' },
                    { label: '2.8.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r2836' },
                    { label: '2.8.3.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r2838' },
                    { label: '2.8.3.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r2839' },
                    { label: '2.8.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r28310' },
                    { label: '2.8.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r28312' },
                    { label: '2.8.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r28313' },
                    { label: '2.8.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r28315' },
                    { label: '2.8.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r28316' },
                    { label: '2.8.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r28317' },
                    { label: '2.8.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r28318' },
                    { label: '2.8.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r28319' },
                    { label: '2.8.3.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r28320' },
                    { label: '2.8.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r28321' },
                    { label: '2.8.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r28322' },
                    { label: '2.8.3.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r28323' },
                    { label: '2.8.3.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r28325' },
                    { label: '2.8.3.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r28326' },
                    { label: '2.8.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r283-' }
                  ]
                },
                {
                  label: '2.8.4 Transferring alkylthio groups',
                  idx: 284,
                  children: [
                    { label: '2.8.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2841' },
                    { label: '2.8.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2842' },
                    { label: '2.8.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2843' },
                    { label: '2.8.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r2844' },
                    { label: '2.8.4.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r2845' }
                  ]
                },
                {
                  label: '2.8.5 Thiosulfotransferases',
                  idx: 285,
                  children: [
                    { label: '2.8.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2851' },
                    { label: '2.8.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2852' }
                  ]
                }
              ]
            },
            {
              label: '2.9 Transferring selenium-containing groups',
              idx: 29,
              children: [
                {
                  label: '2.9.1 Selenotransferases',
                  idx: 291,
                  children: [
                    { label: '2.9.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r2911' },
                    { label: '2.9.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r2912' },
                    { label: '2.9.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r2913' }
                  ]
                }
              ]
            },
            {
              label: '2.10 Transferring molybdenum- or tungsten-containing groups',
              idx: 210,
              children: [
                {
                  label: '2.10.1 Molybdenumtransferases or tungstentransferases with sulfide groups as acceptors',
                  idx: 2101,
                  children: [
                    { label: '2.10.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r21011' }
                  ]
                }
              ]
            }
          ]
        },
        {
          label: '3. Hydrolases',
          idx: 3,
          children: [
            {
              label: '3.1 Acting on ester bonds',
              idx: 31,
              children: [
                {
                  label: '3.1.1 Carboxylic-ester hydrolases',
                  idx: 311,
                  children: [
                    { label: '3.1.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3111' },
                    { label: '3.1.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3112' },
                    { label: '3.1.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r31110' },
                    { label: '3.1.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r31111' },
                    { label: '3.1.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r31113' },
                    { label: '3.1.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r31114' },
                    { label: '3.1.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r31115' },
                    { label: '3.1.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r31117' },
                    { label: '3.1.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r31120' },
                    { label: '3.1.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r311101' },
                    { label: '3.1.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r311102' },
                    { label: '3.1.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r311103' },
                    { label: '3.1.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r311104' },
                    { label: '3.1.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r311105' },
                    { label: '3.1.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r311106' },
                    { label: '3.1.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r311107' },
                    { label: '3.1.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r311108' },
                    { label: '3.1.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r311109' },
                    { label: '3.1.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r311111' },
                    { label: '3.1.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r311112' },
                    { label: '3.1.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r311114' },
                    { label: '3.1.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r311115' },
                    { label: '3.1.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r311116' },
                    { label: '3.1.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r311117' },
                    { label: '3.1.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r311-' }
                  ]
                },
                {
                  label: '3.1.2 Thioester hydrolases',
                  idx: 312,
                  children: [
                    { label: '3.1.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3121' },
                    { label: '3.1.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3122' },
                    { label: '3.1.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3123' },
                    { label: '3.1.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3124' },
                    { label: '3.1.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3125' },
                    { label: '3.1.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3126' },
                    { label: '3.1.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r31211' },
                    { label: '3.1.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r31212' },
                    { label: '3.1.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r31214' },
                    { label: '3.1.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r31215' },
                    { label: '3.1.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r31220' },
                    { label: '3.1.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r31221' },
                    { label: '3.1.2.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r31222' },
                    { label: '3.1.2.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r31223' },
                    { label: '3.1.2.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r31227' },
                    { label: '3.1.2.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r31228' },
                    { label: '3.1.2.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r31229' },
                    { label: '3.1.2.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r31230' },
                    { label: '3.1.2.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r31231' },
                    { label: '3.1.2.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r31232' },
                    { label: '3.1.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r312-' }
                  ]
                },
                {
                  label: '3.1.3 Phosphoric-monoester hydrolases',
                  idx: 313,
                  children: [
                    { label: '3.1.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3131' },
                    { label: '3.1.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3132' },
                    { label: '3.1.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r31310' },
                    { label: '3.1.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r31311' },
                    { label: '3.1.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r31312' },
                    { label: '3.1.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r31313' },
                    { label: '3.1.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r31315' },
                    { label: '3.1.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r31316' },
                    { label: '3.1.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r31318' },
                    { label: '3.1.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r31321' },
                    { label: '3.1.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r31322' },
                    { label: '3.1.3.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r313100' },
                    { label: '3.1.3.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r313101' },
                    { label: '3.1.3.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r313102' },
                    { label: '3.1.3.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r313103' },
                    { label: '3.1.3.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r313104' },
                    { label: '3.1.3.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r313105' },
                    { label: '3.1.3.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r313106' },
                    { label: '3.1.3.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r313108' },
                    { label: '3.1.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r313-' }

                  ]
                },
                {
                  label: '3.1.4 Phosphoric-diester hydrolases',
                  idx: 314,
                  children: [
                    { label: '3.1.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3141' },
                    { label: '3.1.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3142' },
                    { label: '3.1.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3143' },
                    { label: '3.1.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3144' },
                    { label: '3.1.4.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r31410' },
                    { label: '3.1.4.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r31411' },
                    { label: '3.1.4.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r31412' },
                    { label: '3.1.4.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r31414' },
                    { label: '3.1.4.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r31416' },
                    { label: '3.1.4.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r31417' },
                    { label: '3.1.4.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r31423' },
                    { label: '3.1.4.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r31435' },
                    { label: '3.1.4.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r31437' },
                    { label: '3.1.4.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r31438' },
                    { label: '3.1.4.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r31439' },
                    { label: '3.1.4.41 ', children: [{ label: 'Select Enzyme' }], idx: 'r31441' },
                    { label: '3.1.4.43 ', children: [{ label: 'Select Enzyme' }], idx: 'r31443' },
                    { label: '3.1.4.44 ', children: [{ label: 'Select Enzyme' }], idx: 'r31444' },
                    { label: '3.1.4.45 ', children: [{ label: 'Select Enzyme' }], idx: 'r31445' },
                    { label: '3.1.4.46 ', children: [{ label: 'Select Enzyme' }], idx: 'r31446' },
                    { label: '3.1.4.50 ', children: [{ label: 'Select Enzyme' }], idx: 'r31450' },
                    { label: '3.1.4.52 ', children: [{ label: 'Select Enzyme' }], idx: 'r31452' },
                    { label: '3.1.4.53 ', children: [{ label: 'Select Enzyme' }], idx: 'r31453' },
                    { label: '3.1.4.54 ', children: [{ label: 'Select Enzyme' }], idx: 'r31454' },
                    { label: '3.1.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r314-' }
                  ]
                },
                {
                  label: '3.1.5 Triphosphoric-monoester hydrolases',
                  idx: 315,
                  children: [
                    { label: '3.1.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3151' },
                    { label: '3.1.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r315-' }
                  ]
                },
                {
                  label: '3.1.6 Sulfuric-ester hydrolases',
                  idx: 316,
                  children: [
                    { label: '3.1.6.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3161' },
                    { label: '3.1.6.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3162' },
                    { label: '3.1.6.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3164' },
                    { label: '3.1.6.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3166' },
                    { label: '3.1.6.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3168' },
                    { label: '3.1.6.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r31612' },
                    { label: '3.1.6.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r31613' },
                    { label: '3.1.6.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r31614' },
                    { label: '3.1.6.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r31615' },
                    { label: '3.1.6.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r31618' },
                    { label: '3.1.6.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r31619' },
                    { label: '3.1.6.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r31621' },
                    { label: '3.1.6.- ', children: [{ label: 'Select Enzyme' }], idx: 'r316-' }
                  ]
                },
                {
                  label: '3.1.7 Diphosphoric-monoester hydrolases',
                  idx: 317,
                  children: [
                    { label: '3.1.7.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3172' },
                    { label: '3.1.7.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3176' },
                    { label: '3.1.7.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3178' },
                    { label: '3.1.7.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3179' },
                    { label: '3.1.7.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r31710' },
                    { label: '3.1.7.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r31711' },
                    { label: '3.1.7.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r31712' }
                  ]
                },
                {
                  label: '3.1.8 Phosphoric-triester hydrolases',
                  idx: 318,
                  children: [
                    { label: '3.1.8.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3181' },
                    { label: '3.1.8.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3182' }
                  ]
                },
                {
                  label: '3.1.11 Exodeoxyribonucleases producing 5′-phosphomonoesters',
                  idx: 3111,
                  children: [
                    { label: '3.1.11.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31111' },
                    { label: '3.1.11.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r31112' },
                    { label: '3.1.11.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r31113' },
                    { label: '3.1.11.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r31115' },
                    { label: '3.1.11.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r31116' },
                    { label: '3.1.11.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r31117' },
                    { label: '3.1.11.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3111-' }
                  ]
                },
                {
                  label: '3.1.12 Exodeoxyribonucleases producing 3′-phosphomonoesters',
                  idx: 3112,
                  children: [
                    { label: '3.1.12.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31121' },
                    { label: '3.1.12.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r31122' }
                  ]
                },
                {
                  label: '3.1.13 Exoribonucleases producing 5′-phosphomonoesters',
                  idx: 3113,
                  children: [
                    { label: '3.1.13.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31131' },
                    { label: '3.1.13.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r31132' },
                    { label: '3.1.13.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r31133' },
                    { label: '3.1.13.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r31134' },
                    { label: '3.1.13.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r31135' },
                    { label: '3.1.13.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3113-' }
                  ]
                },
                { label: '3.1.14 Exoribonucleases producing 3\'-phosphomonoesters', idx: 3114, children: [{ label: 'Select enzyme' }] },
                {
                  label: '3.1.15 Exonucleases that are active with either ribo- or deoxyribonucleic acids and produce 5\' - phosphomonoesters',
                  idx: 3115,
                  children: [
                    { label: '3.1.15.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3115-' }
                  ]
                },
                {
                  label: '3.1.16 Exonucleases that are active with either ribo- or deoxyribonucleic acids and produce 3\' - phosphomonoesters',
                  idx: 3116,
                  children: [
                    { label: '3.1.16.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31161' }
                  ]
                },
                {
                  label: '3.1.21 Endodeoxyribonucleases producing 5\' - phosphomonoesters',
                  idx: 3121,
                  children: [
                    { label: '3.1.21.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31211' },
                    { label: '3.1.21.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r31212' },
                    { label: '3.1.21.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r31213' },
                    { label: '3.1.21.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r31214' },
                    { label: '3.1.21.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r31215' },
                    { label: '3.1.21.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r31217' },
                    { label: '3.1.21.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r31218' },
                    { label: '3.1.21.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r31219' },
                    { label: '3.1.21.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r312110' },
                    { label: '3.1.21.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3121-' }
                  ]
                },
                {
                  label: '3.1.22 Endodeoxyribonucleases producing 3\' - phosphomonoesters',
                  idx: 3122,
                  children: [
                    { label: '3.1.22.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31221' },
                    { label: '3.1.22.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r31224' },
                    { label: '3.1.22.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3122-' }
                  ]
                },
                { label: '3.1.23 Site-specific endodeoxyribonucleases: cleavage is sequence specific (deleted sub-subclass)', idx: 3123, children: [{ label: 'Select enzyme' }] },
                { label: '3.1.24 Site specific endodeoxyribonucleases: cleavage is not sequence specific (deleted sub-subclass)', idx: 3124, children: [{ label: 'Select enzyme' }] },
                {
                  label: '3.1.25 Site-specific endodeoxyribonucleases that are specific for altered bases',
                  idx: 3125,
                  children: [
                    { label: '3.1.25.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31251' },
                    { label: '3.1.25.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3125-' }
                  ]
                },
                {
                  label: '3.1.26 Endoribonucleases producing 5\' - phosphomonoesters',
                  idx: 3126,
                  children: [
                    { label: '3.1.26.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31261' },
                    { label: '3.1.26.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r31263' },
                    { label: '3.1.26.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r31264' },
                    { label: '3.1.26.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r31265' },
                    { label: '3.1.26.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r31268' },
                    { label: '3.1.26.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r312611' },
                    { label: '3.1.26.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r312612' },
                    { label: '3.1.26.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r312613' },
                    { label: '3.1.26.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3126-' },
                    { label: '3.1.26.n2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3126n2' }
                  ]
                },
                {
                  label: '3.1.27 Endoribonucleases producing 3\' - phosphomonoesters',
                  idx: 3127,
                  children: [
                    { label: '3.1.27.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31271' },
                    { label: '3.1.27.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r31272' },
                    { label: '3.1.27.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r31273' },
                    { label: '3.1.27.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r31274' },
                    { label: '3.1.27.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r31275' },
                    { label: '3.1.27.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r31276' },
                    { label: '3.1.27.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r31279' },
                    { label: '3.1.27.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r312710' },
                    { label: '3.1.27.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3127-' }
                  ]
                },
                {
                  label: '3.1.30 Endoribonucleases that are active with either ribo- or deoxyribonucleic acids and produce 5\' - phosphomonoesters',
                  idx: 3130,
                  children: [
                    { label: '3.1.30.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31301' },
                    { label: '3.1.30.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r31302' },
                    { label: '3.1.30.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3130-' }
                  ]
                },
                {
                  label: '3.1.31 Endoribonucleases that are active with either ribo- or deoxyribonucleic acids and produce 3\' - phosphomonoesters',
                  idx: 3131,
                  children: [
                    { label: '3.1.31.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31311' },
                    { label: '3.1.31.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3131-' }
                  ]
                }
              ]
            },
            {
              label: '3.2 Glycosylases',
              idx: 32,
              children: [
                {
                  label: '3.2.1 Glycosidases, i.e. enzymes that hydrolyse O- and S-glycosyl compounds',
                  idx: 321,
                  children: [
                    { label: '3.2.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3211' },
                    { label: '3.2.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r32110' },
                    { label: '3.2.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r32111' },
                    { label: '3.2.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r321101' },
                    { label: '3.2.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r321102' },
                    { label: '3.2.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r321103' },
                    { label: '3.2.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r321104' },
                    { label: '3.2.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r321105' },
                    { label: '3.2.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r321106' },
                    { label: '3.2.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r321107' },
                    { label: '3.2.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r321108' },
                    { label: '3.2.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r321111' },
                    { label: '3.2.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r321113' },
                    { label: '3.2.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r321114' },
                    { label: '3.2.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r321117' },
                    { label: '3.2.1.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r321118' },
                    { label: '3.2.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r321119' },
                    { label: '3.2.1.122 ', children: [{ label: 'Select Enzyme' }], idx: 'r321122' },
                    { label: '3.2.1.123 ', children: [{ label: 'Select Enzyme' }], idx: 'r321123' },
                    { label: '3.2.1.125 ', children: [{ label: 'Select Enzyme' }], idx: 'r321125' },
                    { label: '3.2.1.126 ', children: [{ label: 'Select Enzyme' }], idx: 'r321126' },
                    { label: '3.2.1.129 ', children: [{ label: 'Select Enzyme' }], idx: 'r321129' },
                    { label: '3.2.1.130 ', children: [{ label: 'Select Enzyme' }], idx: 'r321130' },
                    { label: '3.2.1.131 ', children: [{ label: 'Select Enzyme' }], idx: 'r321131' },
                    { label: '3.2.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r321-' }
                  ]
                },
                {
                  label: '3.2.2 Hydrolysing N-glycosyl compounds',
                  idx: 322,
                  children: [
                    { label: '3.2.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3221' },
                    { label: '3.2.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3222' },
                    { label: '3.2.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3223' },
                    { label: '3.2.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3224' },
                    { label: '3.2.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3225' },
                    { label: '3.2.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3226' },
                    { label: '3.2.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r3227' },
                    { label: '3.2.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3228' },
                    { label: '3.2.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3229' },
                    { label: '3.2.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r32210' },
                    { label: '3.2.2.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r32216' },
                    { label: '3.2.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r32217' },
                    { label: '3.2.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r32219' },
                    { label: '3.2.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r32220' },
                    { label: '3.2.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r32221' },
                    { label: '3.2.2.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r32222' },
                    { label: '3.2.2.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r32223' },
                    { label: '3.2.2.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r32224' },
                    { label: '3.2.2.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r32226' },
                    { label: '3.2.2.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r32227' },
                    { label: '3.2.2.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r32228' },
                    { label: '3.2.2.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r32229' },
                    { label: '3.2.2.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r32230' },
                    { label: '3.2.2.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r32231' },
                    { label: '3.2.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r322-' }
                  ]
                },
                {
                  label: '3.2.3 Hydrolysing S-glycosyl compounds (deleted sub-subclass)',
                  idx: 323,
                  children: [
                    { label: '3.2.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3231' }

                  ]
                }
              ]
            },
            {
              label: '3.3 Acting on ether bonds',
              idx: 33,
              children: [
                {
                  label: '3.3.1 Thioether and trialkylsulfonium hydrolases',
                  idx: 331,
                  children: [
                    { label: '3.3.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3311' },
                    { label: '3.3.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3312' }
                  ]
                },
                {
                  label: '3.3.2 Ether hydrolases',
                  idx: 332,
                  children: [
                    { label: '3.3.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3321' },
                    { label: '3.3.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3322' },
                    { label: '3.3.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3323' },
                    { label: '3.3.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3326' },
                    { label: '3.3.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3328' },
                    { label: '3.3.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3329' },
                    { label: '3.3.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r33210' },
                    { label: '3.3.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r33211' },
                    { label: '3.3.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r33212' },
                    { label: '3.3.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r33213' },
                    { label: '3.3.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r33214' },
                    { label: '3.3.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r33215' },
                    { label: '3.3.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r332-' }

                  ]
                }
              ]
            },
            {
              label: '3.4 Acting on peptide bonds (peptidases)',
              idx: 34,
              children: [
                { label: '3.4.1 α-Amino-acyl-peptide hydrolases (deleted sub-subclass)', idx: 341, children: [{ label: 'Select enzyme' }] },
                { label: '3.4.2 Peptidyl-amino-acid hydrolases (deleted sub-subclass)', idx: 342, children: [{ label: 'Select enzyme' }] },
                { label: '3.4.3 Dipeptide hydrolases (deleted sub-subclass)', idx: 343, children: [{ label: 'Select enzyme' }] },
                { label: '3.4.4 Peptidyl peptide hydrolases (deleted sub-subclass)', idx: 344, children: [{ label: 'Select enzyme' }] },
                {
                  label: '3.4.11 Aminopeptidases',
                  idx: 3411,
                  children: [
                    { label: '3.4.11.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34111' },
                    { label: '3.4.11.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r34112' },
                    { label: '3.4.11.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r34113' },
                    { label: '3.4.11.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r34114' },
                    { label: '3.4.11.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r34115' },
                    { label: '3.4.11.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r34116' },
                    { label: '3.4.11.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r34117' },
                    { label: '3.4.11.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r34119' },
                    { label: '3.4.11.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r341110' },
                    { label: '3.4.11.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r341114' },
                    { label: '3.4.11.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r341115' },
                    { label: '3.4.11.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r341117' },
                    { label: '3.4.11.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r341118' },
                    { label: '3.4.11.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r341119' },
                    { label: '3.4.11.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r341120' },
                    { label: '3.4.11.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r341121' },
                    { label: '3.4.11.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r341122' },
                    { label: '3.4.11.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r341123' },
                    { label: '3.4.11.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r341124' },
                    { label: '3.4.11.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r341125' },
                    { label: '3.4.11.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r341126' },
                    { label: '3.4.11.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3411-' }
                  ]
                },
                { label: '3.4.12 Peptidylamino-acid hydrolases or acylamino-acid hydrolases (deleted sub-subclass)', idx: 3412, children: [{ label: 'Select enzyme' }] },
                {
                  label: '3.4.13 Dipeptidases',
                  idx: 3413,
                  children: [
                    { label: '3.4.13.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r34133' },
                    { label: '3.4.13.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r34134' },
                    { label: '3.4.13.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r34139' },
                    { label: '3.4.13.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r341318' },
                    { label: '3.4.13.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r341319' },
                    { label: '3.4.13.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r341320' },
                    { label: '3.4.13.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r341321' },
                    { label: '3.4.13.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r341322' },
                    { label: '3.4.13.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r341323' },
                    { label: '3.4.13.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3413-' }

                  ]
                },
                {
                  label: '3.4.14 Dipeptidyl-peptidases and tripeptidyl-peptidases',
                  idx: 3414,
                  children: [
                    { label: '3.4.14.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34141' },
                    { label: '3.4.14.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r34142' },
                    { label: '3.4.14.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r34144' },
                    { label: '3.4.14.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r34145' },
                    { label: '3.4.14.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r34149' },
                    { label: '3.4.14.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r341410' },
                    { label: '3.4.14.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r341411' },
                    { label: '3.4.14.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r341412' },
                    { label: '3.4.14.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r341413' },
                    { label: '3.4.14.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3414-' }
                  ]
                },
                {
                  label: '3.4.15 Peptidyl-dipeptidases',
                  idx: 3415,
                  children: [
                    { label: '3.4.15.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34151' },
                    { label: '3.4.15.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r34155' },
                    { label: '3.4.15.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r34156' }
                  ]
                },
                {
                  label: '3.4.16 Serine-type carboxypeptidases',
                  idx: 3416,
                  children: [
                    { label: '3.4.16.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34161' },
                    { label: '3.4.16.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r34162' },
                    { label: '3.4.16.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r34164' },
                    { label: '3.4.16.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r34165' },
                    { label: '3.4.16.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r34166' },
                    { label: '3.4.16.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3416-' }

                  ]
                },
                {
                  label: '3.4.17 Metallocarboxypeptidases',
                  idx: 3417,
                  children: [
                    { label: '3.4.17.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34171' },
                    { label: '3.4.17.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r34172' },
                    { label: '3.4.17.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r34173' },
                    { label: '3.4.17.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r34174' },
                    { label: '3.4.17.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r34176' },
                    { label: '3.4.17.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r34178' },
                    { label: '3.4.17.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r341710' },
                    { label: '3.4.17.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r341711' },
                    { label: '3.4.17.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r341712' },
                    { label: '3.4.17.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r341713' },
                    { label: '3.4.17.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r341714' },
                    { label: '3.4.17.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r341715' },
                    { label: '3.4.17.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r341717' },
                    { label: '3.4.17.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r341718' },
                    { label: '3.4.17.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r341719' },
                    { label: '3.4.17.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r341720' },
                    { label: '3.4.17.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r341721' },
                    { label: '3.4.17.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r341722' },
                    { label: '3.4.17.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r341723' },
                    { label: '3.4.17.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r341724' },
                    { label: '3.4.17.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3417-' }

                  ]
                },
                {
                  label: '3.4.18 Cysteine-type carboxypeptidases',
                  idx: 3418,
                  children: [
                    { label: '3.4.18.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34181' }
                  ]
                },
                {
                  label: '3.4.19 Omega peptidases',
                  idx: 3419,
                  children: [
                    { label: '3.4.19.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34191' },
                    { label: '3.4.19.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r34193' },
                    { label: '3.4.19.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r34195' },
                    { label: '3.4.19.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r34196' },
                    { label: '3.4.19.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r34199' },
                    { label: '3.4.19.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r341911' },
                    { label: '3.4.19.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r341912' },
                    { label: '3.4.19.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r341913' },
                    { label: '3.4.19.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r341914' },
                    { label: '3.4.19.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r341915' },
                    { label: '3.4.19.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r341916' },
                    { label: '3.4.19.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3419-' }
                  ]
                },
                {
                  label: '3.4.21 Serine endopeptidases',
                  idx: 3421,
                  children: [
                    { label: '3.4.21.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34211' },
                    { label: '3.4.21.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r342110' },
                    { label: '3.4.21.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r342111' },
                    { label: '3.4.21.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r342112' },
                    { label: '3.4.21.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421100' },
                    { label: '3.4.21.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421101' },
                    { label: '3.4.21.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421102' },
                    { label: '3.4.21.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421103' },
                    { label: '3.4.21.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421104' },
                    { label: '3.4.21.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421105' },
                    { label: '3.4.21.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421106' },
                    { label: '3.4.21.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421107' },
                    { label: '3.4.21.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421108' },
                    { label: '3.4.21.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421109' },
                    { label: '3.4.21.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421110' },
                    { label: '3.4.21.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421111' },
                    { label: '3.4.21.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421112' },
                    { label: '3.4.21.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421113' },
                    { label: '3.4.21.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421114' },
                    { label: '3.4.21.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421115' },
                    { label: '3.4.21.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421116' },
                    { label: '3.4.21.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421117' },
                    { label: '3.4.21.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421118' },
                    { label: '3.4.21.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r3421119' },
                    { label: '3.4.21.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3421-' }
                  ]
                },
                {
                  label: '3.4.22 Cysteine endopeptidases',
                  idx: 3422,
                  children: [
                    { label: '3.4.22.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34221' },
                    { label: '3.4.22.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r34222' },
                    { label: '3.4.22.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r34223' },
                    { label: '3.4.22.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r342210' },
                    { label: '3.4.22.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r342212' },
                    { label: '3.4.22.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r342214' },
                    { label: '3.4.22.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r342215' },
                    { label: '3.4.22.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r342216' },
                    { label: '3.4.22.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r342217' },
                    { label: '3.4.22.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r342225' },
                    { label: '3.4.22.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r342227' },
                    { label: '3.4.22.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r342228' },
                    { label: '3.4.22.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r342229' },
                    { label: '3.4.22.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r342230' },
                    { label: '3.4.22.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r342231' },
                    { label: '3.4.22.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r342232' },
                    { label: '3.4.22.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r342233' },
                    { label: '3.4.22.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r342234' },
                    { label: '3.4.22.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r342235' },
                    { label: '3.4.22.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r342236' },
                    { label: '3.4.22.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r342237' },
                    { label: '3.4.22.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r342238' },
                    { label: '3.4.22.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r342239' },
                    { label: '3.4.22.40 ', children: [{ label: 'Select Enzyme' }], idx: 'r342240' },
                    { label: '3.4.22.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3422-' }
                  ]
                },
                {
                  label: '3.4.23 Aspartic endopeptidases',
                  idx: 3423,
                  children: [
                    { label: '3.4.23.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34231' },
                    { label: '3.4.23.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r34232' },
                    { label: '3.4.23.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r34233' },
                    { label: '3.4.23.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r34234' },
                    { label: '3.4.23.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r342310' },
                    { label: '3.4.23.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r342312' },
                    { label: '3.4.23.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r342315' },
                    { label: '3.4.23.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r342316' },
                    { label: '3.4.23.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r342318' },
                    { label: '3.4.23.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r342319' },
                    { label: '3.4.23.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r342320' },
                    { label: '3.4.23.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r342321' },
                    { label: '3.4.23.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r342322' },
                    { label: '3.4.23.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r342323' },
                    { label: '3.4.23.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r342324' },
                    { label: '3.4.23.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r342325' },
                    { label: '3.4.23.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r342329' },
                    { label: '3.4.23.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r342332' },
                    { label: '3.4.23.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r342334' },
                    { label: '3.4.23.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r342335' },
                    { label: '3.4.23.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r342336' },
                    { label: '3.4.23.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r342337' },
                    { label: '3.4.23.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r342338' },
                    { label: '3.4.23.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r342339' },
                    { label: '3.4.23.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3423-' }
                  ]
                },
                {
                  label: '3.4.24 Metalloendopeptidases',
                  idx: 3424,
                  children: [
                    { label: '3.4.24.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34241' },
                    { label: '3.4.24.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r34243' },
                    { label: '3.4.24.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r342411' },
                    { label: '3.4.24.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r342412' },
                    { label: '3.4.24.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r342413' },
                    { label: '3.4.24.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r342414' },
                    { label: '3.4.24.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r342415' },
                    { label: '3.4.24.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r342416' },
                    { label: '3.4.24.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r342417' },
                    { label: '3.4.24.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r342418' },
                    { label: '3.4.24.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r342419' },
                    { label: '3.4.24.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r342420' },
                    { label: '3.4.24.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r342421' },
                    { label: '3.4.24.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r342422' },
                    { label: '3.4.24.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r342423' },
                    { label: '3.4.24.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r342424' },
                    { label: '3.4.24.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r342425' },
                    { label: '3.4.24.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r342426' },
                    { label: '3.4.24.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r342427' },
                    { label: '3.4.24.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r342428' },
                    { label: '3.4.24.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r342429' },
                    { label: '3.4.24.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r342430' },
                    { label: '3.4.24.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r342431' },
                    { label: '3.4.24.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r342432' },
                    { label: '3.4.24.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3424-' }

                  ]
                },
                {
                  label: '3.4.25 Threonine endopeptidases',
                  idx: 3425,
                  children: [
                    { label: '3.4.25.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r34251' },
                    { label: '3.4.25.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r34252' },
                    { label: '3.4.25.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3425-' }

                  ]
                },
                {
                  label: '3.4.99 Endopeptidases of unknown catalytic mechanism (sub-subclass is currently empty)',
                  idx: 3499,
                  children: [
                    { label: '3.4.99.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r349937' },
                    { label: '3.4.99.46 ', children: [{ label: 'Select Enzyme' }], idx: 'r349946' }
                  ]
                }
              ]
            },
            {
              label: '3.5 Acting on carbon-nitrogen bonds, other than peptide bonds',
              idx: 35,
              children: [
                {
                  label: '3.5.1 In linear amides',
                  idx: 351,
                  children: [
                    { label: '3.5.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3511' },
                    { label: '3.5.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r35110' },
                    { label: '3.5.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r35111' },
                    { label: '3.5.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r35112' },
                    { label: '3.5.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r351100' },
                    { label: '3.5.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r351101' },
                    { label: '3.5.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r351102' },
                    { label: '3.5.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r351103' },
                    { label: '3.5.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r351104' },
                    { label: '3.5.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r351105' },
                    { label: '3.5.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r351106' },
                    { label: '3.5.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r351107' },
                    { label: '3.5.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r351108' },
                    { label: '3.5.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r351110' },
                    { label: '3.5.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r351111' },
                    { label: '3.5.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r351112' },
                    { label: '3.5.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r351113' },
                    { label: '3.5.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r351114' },
                    { label: '3.5.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r351115' },
                    { label: '3.5.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r351116' },
                    { label: '3.5.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r351117' },
                    { label: '3.5.1.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r351118' },
                    { label: '3.5.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r351119' },
                    { label: '3.5.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r351121' },
                    { label: '3.5.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r351-' }
                  ]
                },
                {
                  label: '3.5.2 In cyclic amides',
                  idx: 352,
                  children: [
                    { label: '3.5.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3521' },
                    { label: '3.5.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3522' },
                    { label: '3.5.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3523' },
                    { label: '3.5.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3525' },
                    { label: '3.5.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3526' },
                    { label: '3.5.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r3527' },
                    { label: '3.5.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3529' },
                    { label: '3.5.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r35210' },
                    { label: '3.5.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r35212' },
                    { label: '3.5.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r35215' },
                    { label: '3.5.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r35217' },
                    { label: '3.5.2.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r35218' },
                    { label: '3.5.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r35219' },
                    { label: '3.5.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r35220' },
                    { label: '3.5.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r352-' }
                  ]
                },
                {
                  label: '3.5.3 In linear amidines',
                  idx: 353,
                  children: [
                    { label: '3.5.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3531' },
                    { label: '3.5.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3533' },
                    { label: '3.5.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3534' },
                    { label: '3.5.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3536' },
                    { label: '3.5.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r3537' },
                    { label: '3.5.3.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3538' },
                    { label: '3.5.3.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3539' },
                    { label: '3.5.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r35310' },
                    { label: '3.5.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r35311' },
                    { label: '3.5.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r35312' },
                    { label: '3.5.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r35315' },
                    { label: '3.5.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r35317' },
                    { label: '3.5.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r35318' },
                    { label: '3.5.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r35319' },
                    { label: '3.5.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r35322' },
                    { label: '3.5.3.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r35323' },
                    { label: '3.5.3.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r35324' },
                    { label: '3.5.3.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r35325' },
                    { label: '3.5.3.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r35326' },
                    { label: '3.5.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r353-' }
                  ]
                },
                {
                  label: '3.5.4 In cyclic amidines',
                  idx: 354,
                  children: [
                    { label: '3.5.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3541' },
                    { label: '3.5.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3542' },
                    { label: '3.5.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3543' },
                    { label: '3.5.4.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r35410' },
                    { label: '3.5.4.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r35411' },
                    { label: '3.5.4.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r35412' },
                    { label: '3.5.4.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r35413' },
                    { label: '3.5.4.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r35415' },
                    { label: '3.5.4.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r35416' },
                    { label: '3.5.4.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r35419' },
                    { label: '3.5.4.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r35422' },
                    { label: '3.5.4.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r35423' },
                    { label: '3.5.4.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r35425' },
                    { label: '3.5.4.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r35426' },
                    { label: '3.5.4.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r35427' },
                    { label: '3.5.4.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r35428' },
                    { label: '3.5.4.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r35429' },
                    { label: '3.5.4.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r35430' },
                    { label: '3.5.4.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r35431' },
                    { label: '3.5.4.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r35432' },
                    { label: '3.5.4.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r35433' },
                    { label: '3.5.4.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r35434' },
                    { label: '3.5.4.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r35435' },
                    { label: '3.5.4.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r35436' },
                    { label: '3.5.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r354-' }
                  ]
                },
                {
                  label: '3.5.5 In nitriles',
                  idx: 355,
                  children: [
                    { label: '3.5.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3551' },
                    { label: '3.5.5.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3554' },
                    { label: '3.5.5.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3555' },
                    { label: '3.5.5.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r3557' },
                    { label: '3.5.5.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3558' }
                  ]
                },
                {
                  label: '3.5.99 In other compounds',
                  idx: 3599,
                  children: [
                    { label: '3.5.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r35992' },
                    { label: '3.5.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r35994' },
                    { label: '3.5.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r35995' },
                    { label: '3.5.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r35996' },
                    { label: '3.5.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r35997' },
                    { label: '3.5.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r35998' },
                    { label: '3.5.99.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r35999' },
                    { label: '3.5.99.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r359910' },
                    { label: '3.5.99.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r359911' },
                    { label: '3.5.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r3599-' }
                  ]
                }
              ]
            },
            {
              label: '3.6 Acting on acid anhydrides',
              idx: 36,
              children: [
                {
                  label: '3.6.1 In phosphorus-containing anhydrides',
                  idx: 361,
                  children: [
                    { label: '3.6.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3611' },
                    { label: '3.6.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3613' },
                    { label: '3.6.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3614' },
                    { label: '3.6.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r36110' },
                    { label: '3.6.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r36111' },
                    { label: '3.6.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r36112' },
                    { label: '3.6.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r36113' },
                    { label: '3.6.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r36114' },
                    { label: '3.6.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r36115' },
                    { label: '3.6.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r36116' },
                    { label: '3.6.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r36117' },
                    { label: '3.6.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r36118' },
                    { label: '3.6.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r36119' },
                    { label: '3.6.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r36121' },
                    { label: '3.6.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r36122' },
                    { label: '3.6.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r36123' },
                    { label: '3.6.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r36125' },
                    { label: '3.6.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r36126' },
                    { label: '3.6.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r36127' },
                    { label: '3.6.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r36128' },
                    { label: '3.6.1.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r36129' },
                    { label: '3.6.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r36130' },
                    { label: '3.6.1.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r36131' },
                    { label: '3.6.1.40 ', children: [{ label: 'Select Enzyme' }], idx: 'r36140' },
                    { label: '3.6.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r361-' }
                  ]
                },
                {
                  label: '3.6.2 In sulfonyl-containing anhydrides',
                  idx: 362,
                  children: [
                    { label: '3.6.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3621' }
                  ]
                },
                {
                  label: '3.6.3 Acting on acid anhydrides to catalyse transmembrane movement of substances',
                  idx: 363,
                  children: [
                    { label: '3.6.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3631' },
                    { label: '3.6.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3632' },
                    { label: '3.6.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3633' },
                    { label: '3.6.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3634' },
                    { label: '3.6.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3635' },
                    { label: '3.6.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r36310' },
                    { label: '3.6.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r36312' },
                    { label: '3.6.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r36314' },
                    { label: '3.6.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r36315' },
                    { label: '3.6.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r36316' },
                    { label: '3.6.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r36317' },
                    { label: '3.6.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r36319' },
                    { label: '3.6.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r36321' },
                    { label: '3.6.3.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r36324' },
                    { label: '3.6.3.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r36325' },
                    { label: '3.6.3.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r36330' },
                    { label: '3.6.3.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r36332' },
                    { label: '3.6.3.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r36333' },
                    { label: '3.6.3.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r36334' },
                    { label: '3.6.3.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r36339' },
                    { label: '3.6.3.43 ', children: [{ label: 'Select Enzyme' }], idx: 'r36343' },
                    { label: '3.6.3.44 ', children: [{ label: 'Select Enzyme' }], idx: 'r36344' },
                    { label: '3.6.3.49 ', children: [{ label: 'Select Enzyme' }], idx: 'r36349' },
                    { label: '3.6.3.51 ', children: [{ label: 'Select Enzyme' }], idx: 'r36351' },
                    { label: '3.6.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r363-' }
                  ]
                },
                {
                  label: '3.6.4 Acting on acid anhydrides to facilitate cellular and subcellular movement',
                  idx: 364,
                  children: [
                    { label: '3.6.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3641' },
                    { label: '3.6.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3643' },
                    { label: '3.6.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3644' },
                    { label: '3.6.4.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3646' },
                    { label: '3.6.4.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3648' },
                    { label: '3.6.4.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3649' },
                    { label: '3.6.4.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r36410' },
                    { label: '3.6.4.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r36412' },
                    { label: '3.6.4.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r36413' },
                    { label: '3.6.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r364-' }
                  ]
                },
                {
                  label: '3.6.5 Acting on GTP to facilitate cellular and subcellular movement',
                  idx: 365,
                  children: [
                    { label: '3.6.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3651' },
                    { label: '3.6.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3652' },
                    { label: '3.6.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3653' },
                    { label: '3.6.5.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3654' },
                    { label: '3.6.5.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3655' },
                    { label: '3.6.5.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3656' },
                    { label: '3.6.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r365-' },
                    { label: '3.6.5.n1 ', children: [{ label: 'Select Enzyme' }], idx: 'r365n1' }
                  ]
                }
              ]
            },
            {
              label: '3.7 Acting on carbon-carbon bonds',
              idx: 37,
              children: [
                {
                  label: '3.7.1 In ketonic substances',
                  idx: 371,
                  children: [
                    { label: '3.7.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3711' },
                    { label: '3.7.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3712' },
                    { label: '3.7.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3713' },
                    { label: '3.7.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r3714' },
                    { label: '3.7.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3715' },
                    { label: '3.7.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r3717' },
                    { label: '3.7.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3718' },
                    { label: '3.7.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3719' },
                    { label: '3.7.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r37111' },
                    { label: '3.7.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r37112' },
                    { label: '3.7.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r37113' },
                    { label: '3.7.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r37114' },
                    { label: '3.7.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r37117' },
                    { label: '3.7.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r37118' },
                    { label: '3.7.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r37119' },
                    { label: '3.7.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r37120' },
                    { label: '3.7.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r37121' },
                    { label: '3.7.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r37122' },
                    { label: '3.7.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r37123' },
                    { label: '3.7.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r37124' },
                    { label: '3.7.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r37125' },
                    { label: '3.7.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r37127' },
                    { label: '3.7.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r371-' }
                  ]
                }
              ]
            },
            {
              label: '3.8 Acting on halide bonds',
              idx: 38,
              children: [
                {
                  label: '3.8.1 In carbon-halide compounds',
                  idx: 381,
                  children: [
                    { label: '3.8.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3811' },
                    { label: '3.8.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3812' },
                    { label: '3.8.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3813' },
                    { label: '3.8.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r3815' },
                    { label: '3.8.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r3816' },
                    { label: '3.8.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r3817' },
                    { label: '3.8.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r3818' },
                    { label: '3.8.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r3819' },
                    { label: '3.8.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r38110' },
                    { label: '3.8.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r381-' }
                  ]
                },
                { label: '3.8.2 In phosphorus-halide compounds (deleted sub-subclass)', idx: 382, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '3.9 Acting on phosphorus-nitrogen bonds',
              idx: 39,
              children: [
                {
                  label: '3.9.1 Acting on phosphorus-nitrogen bonds (only sub-subclass identified to date)',
                  idx: 391,
                  children: [
                    { label: '3.9.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r3911' },
                    { label: '3.9.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r3912' },
                    { label: '3.9.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r3913' },
                    { label: '3.9.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r391-' }
                  ]
                }
              ]
            },
            {
              label: '3.10 Acting on sulfur-nitrogen bonds',
              idx: 310,
              children: [
                {
                  label: '3.10.1 Acting on sulfur-nitrogen bonds (only sub-subclass identified to date)',
                  idx: 3101,
                  children: [
                    { label: '3.10.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31011' }
                  ]
                }
              ]
            },
            {
              label: '3.11 Acting on carbon-phosphorus bonds',
              idx: 311,
              children: [
                {
                  label: '3.11.1 Acting on carbon-phosphorus bonds (only sub-subclass identified to date)',
                  idx: 3111,
                  children: [
                    { label: '3.11.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r31111' },
                    { label: '3.11.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r31112' },
                    { label: '3.11.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r31113' }
                  ]
                }
              ]
            },
            {
              label: '3.12 Acting on sulfur-sulfur bonds',
              idx: 312,
              children: [
                { label: '3.12.1 Acting on sulfur-sulfur bonds (only sub-subclass identified to date)', idx: 3121, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '3.13 Acting on carbon-sulfur bonds',
              idx: 313,
              children: [
                { label: '3.13.1 Acting on carbon-sulfur bonds (only sub-subclass identified to date)', idx: 3131, children: [{ label: 'Select enzyme' }] }
              ]
            }
          ]
        },
        {
          label: '4. Lyases',
          idx: 4,
          children: [
            {
              label: '4.1 Carbon-carbon lyases',
              idx: 41,
              children: [
                {
                  label: '4.1.1 Carboxy-lyases',
                  idx: 411,
                  children: [
                    { label: '4.1.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4111' },
                    { label: '4.1.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r41111' },
                    { label: '4.1.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r41112' },
                    { label: '4.1.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r41115' },
                    { label: '4.1.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r41117' },
                    { label: '4.1.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r411100' },
                    { label: '4.1.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r411101' },
                    { label: '4.1.1.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r411102' },
                    { label: '4.1.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r411103' },
                    { label: '4.1.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r411104' },
                    { label: '4.1.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r411105' },
                    { label: '4.1.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r411106' },
                    { label: '4.1.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r411107' },
                    { label: '4.1.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r411108' },
                    { label: '4.1.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r411109' },
                    { label: '4.1.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r411110' },
                    { label: '4.1.1.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r411111' },
                    { label: '4.1.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r411112' },
                    { label: '4.1.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r411113' },
                    { label: '4.1.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r411114' },
                    { label: '4.1.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r411116' },
                    { label: '4.1.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r411117' },
                    { label: '4.1.1.120 ', children: [{ label: 'Select Enzyme' }], idx: 'r411120' },
                    { label: '4.1.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r411121' },
                    { label: '4.1.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r411-' }
                  ]
                },
                {
                  label: '4.1.2 Aldehyde-lyases',
                  idx: 412,
                  children: [
                    { label: '4.1.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r4124' },
                    { label: '4.1.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r41210' },
                    { label: '4.1.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r41211' },
                    { label: '4.1.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r41213' },
                    { label: '4.1.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r41214' },
                    { label: '4.1.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r41215' },
                    { label: '4.1.2.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r41216' },
                    { label: '4.1.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r41217' },
                    { label: '4.1.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r41219' },
                    { label: '4.1.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r41220' },
                    { label: '4.1.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r41221' },
                    { label: '4.1.2.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r41222' },
                    { label: '4.1.2.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r41225' },
                    { label: '4.1.2.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r41226' },
                    { label: '4.1.2.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r41227' },
                    { label: '4.1.2.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r41228' },
                    { label: '4.1.2.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r41229' },
                    { label: '4.1.2.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r41230' },
                    { label: '4.1.2.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r41234' },
                    { label: '4.1.2.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r41237' },
                    { label: '4.1.2.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r41238' },
                    { label: '4.1.2.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r41239' },
                    { label: '4.1.2.40 ', children: [{ label: 'Select Enzyme' }], idx: 'r41240' },
                    { label: '4.1.2.41 ', children: [{ label: 'Select Enzyme' }], idx: 'r41241' },
                    { label: '4.1.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r412-' }
                  ]
                },
                {
                  label: '4.1.3 Oxo-acid-lyases',
                  idx: 413,
                  children: [
                    { label: '4.1.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4131' },
                    { label: '4.1.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r4132' },
                    { label: '4.1.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r4133' },
                    { label: '4.1.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r4134' },
                    { label: '4.1.3.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r41316' },
                    { label: '4.1.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r41317' },
                    { label: '4.1.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r41318' },
                    { label: '4.1.3.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r41323' },
                    { label: '4.1.3.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r41324' },
                    { label: '4.1.3.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r41325' },
                    { label: '4.1.3.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r41326' },
                    { label: '4.1.3.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r41327' },
                    { label: '4.1.3.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r41330' },
                    { label: '4.1.3.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r41332' },
                    { label: '4.1.3.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r41334' },
                    { label: '4.1.3.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r41336' },
                    { label: '4.1.3.38 ', children: [{ label: 'Select Enzyme' }], idx: 'r41338' },
                    { label: '4.1.3.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r41339' },
                    { label: '4.1.3.40 ', children: [{ label: 'Select Enzyme' }], idx: 'r41340' },
                    { label: '4.1.3.41 ', children: [{ label: 'Select Enzyme' }], idx: 'r41341' },
                    { label: '4.1.3.43 ', children: [{ label: 'Select Enzyme' }], idx: 'r41343' },
                    { label: '4.1.3.44 ', children: [{ label: 'Select Enzyme' }], idx: 'r41344' },
                    { label: '4.1.3.45 ', children: [{ label: 'Select Enzyme' }], idx: 'r41345' },
                    { label: '4.1.3.46 ', children: [{ label: 'Select Enzyme' }], idx: 'r41346' },
                    { label: '4.1.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r413-' },
                    { label: '4.1.3. ', children: [{ label: 'Select Enzyme' }], idx: 'r413' }
                  ]
                },
                {
                  label: '4.1.99 Other carbon-carbon lyases',
                  idx: 4199,
                  children: [
                    { label: '4.1.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r41991' },
                    { label: '4.1.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r41992' },
                    { label: '4.1.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r41993' },
                    { label: '4.1.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r41994' },
                    { label: '4.1.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r41995' },
                    { label: '4.1.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r41996' },
                    { label: '4.1.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r41997' },
                    { label: '4.1.99.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r419911' },
                    { label: '4.1.99.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r419912' },
                    { label: '4.1.99.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r419913' },
                    { label: '4.1.99.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r419914' },
                    { label: '4.1.99.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r419916' },
                    { label: '4.1.99.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r419917' },
                    { label: '4.1.99.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r419919' },
                    { label: '4.1.99.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r419920' },
                    { label: '4.1.99.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r419922' },
                    { label: '4.1.99.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r419923' },
                    { label: '4.1.99.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r419924' },
                    { label: '4.1.99.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r419925' },
                    { label: '4.1.99.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r419926' },
                    { label: '4.1.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r4199-' }
                  ]
                }
              ]
            },
            {
              label: '4.2 Carbon-oxygen lyases',
              idx: 42,
              children: [
                {
                  label: '4.2.1 Hydro-lyases',
                  idx: 421,
                  children: [
                    { label: '4.2.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4211' },
                    { label: '4.2.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r42110' },
                    { label: '4.2.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r42111' },
                    { label: '4.2.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r42112' },
                    { label: '4.2.1.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r421100' },
                    { label: '4.2.1.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r421101' },
                    { label: '4.2.1.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r421103' },
                    { label: '4.2.1.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r421104' },
                    { label: '4.2.1.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r421105' },
                    { label: '4.2.1.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r421106' },
                    { label: '4.2.1.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r421107' },
                    { label: '4.2.1.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r421108' },
                    { label: '4.2.1.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r421109' },
                    { label: '4.2.1.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r421110' },
                    { label: '4.2.1.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r421112' },
                    { label: '4.2.1.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r421113' },
                    { label: '4.2.1.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r421114' },
                    { label: '4.2.1.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r421115' },
                    { label: '4.2.1.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r421116' },
                    { label: '4.2.1.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r421117' },
                    { label: '4.2.1.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r421118' },
                    { label: '4.2.1.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r421119' },
                    { label: '4.2.1.120 ', children: [{ label: 'Select Enzyme' }], idx: 'r421120' },
                    { label: '4.2.1.121 ', children: [{ label: 'Select Enzyme' }], idx: 'r421121' },
                    { label: '4.2.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r421-' }
                  ]
                },
                {
                  label: '4.2.2 Acting on polysaccharides',
                  idx: 422,
                  children: [
                    { label: '4.2.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4221' },
                    { label: '4.2.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r4222' },
                    { label: '4.2.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r4223' },
                    { label: '4.2.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r4224' },
                    { label: '4.2.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r4225' },
                    { label: '4.2.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r4226' },
                    { label: '4.2.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r4227' },
                    { label: '4.2.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r42210' },
                    { label: '4.2.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r42211' },
                    { label: '4.2.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r42212' },
                    { label: '4.2.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r42213' },
                    { label: '4.2.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r42214' },
                    { label: '4.2.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r42215' },
                    { label: '4.2.2.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r42216' },
                    { label: '4.2.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r42217' },
                    { label: '4.2.2.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r42218' },
                    { label: '4.2.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r42219' },
                    { label: '4.2.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r42220' },
                    { label: '4.2.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r42221' },
                    { label: '4.2.2.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r42222' },
                    { label: '4.2.2.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r42223' },
                    { label: '4.2.2.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r42224' },
                    { label: '4.2.2.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r42225' },
                    { label: '4.2.2.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r42226' },
                    { label: '4.2.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r422-' }
                  ]
                },
                {
                  label: '4.2.3 Acting on phosphates',
                  idx: 423,
                  children: [
                    { label: '4.2.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4231' },
                    { label: '4.2.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r42310' },
                    { label: '4.2.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r42311' },
                    { label: '4.2.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r42312' },
                    { label: '4.2.3.100 ', children: [{ label: 'Select Enzyme' }], idx: 'r423100' },
                    { label: '4.2.3.101 ', children: [{ label: 'Select Enzyme' }], idx: 'r423101' },
                    { label: '4.2.3.102 ', children: [{ label: 'Select Enzyme' }], idx: 'r423102' },
                    { label: '4.2.3.103 ', children: [{ label: 'Select Enzyme' }], idx: 'r423103' },
                    { label: '4.2.3.104 ', children: [{ label: 'Select Enzyme' }], idx: 'r423104' },
                    { label: '4.2.3.105 ', children: [{ label: 'Select Enzyme' }], idx: 'r423105' },
                    { label: '4.2.3.106 ', children: [{ label: 'Select Enzyme' }], idx: 'r423106' },
                    { label: '4.2.3.107 ', children: [{ label: 'Select Enzyme' }], idx: 'r423107' },
                    { label: '4.2.3.108 ', children: [{ label: 'Select Enzyme' }], idx: 'r423108' },
                    { label: '4.2.3.109 ', children: [{ label: 'Select Enzyme' }], idx: 'r423109' },
                    { label: '4.2.3.110 ', children: [{ label: 'Select Enzyme' }], idx: 'r423110' },
                    { label: '4.2.3.111 ', children: [{ label: 'Select Enzyme' }], idx: 'r423111' },
                    { label: '4.2.3.112 ', children: [{ label: 'Select Enzyme' }], idx: 'r423112' },
                    { label: '4.2.3.113 ', children: [{ label: 'Select Enzyme' }], idx: 'r423113' },
                    { label: '4.2.3.114 ', children: [{ label: 'Select Enzyme' }], idx: 'r423114' },
                    { label: '4.2.3.115 ', children: [{ label: 'Select Enzyme' }], idx: 'r423115' },
                    { label: '4.2.3.116 ', children: [{ label: 'Select Enzyme' }], idx: 'r423116' },
                    { label: '4.2.3.117 ', children: [{ label: 'Select Enzyme' }], idx: 'r423117' },
                    { label: '4.2.3.118 ', children: [{ label: 'Select Enzyme' }], idx: 'r423118' },
                    { label: '4.2.3.119 ', children: [{ label: 'Select Enzyme' }], idx: 'r423119' },
                    { label: '4.2.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r423-' }
                  ]
                },
                {
                  label: '4.2.99 Other carbon-oxygen lyases',
                  idx: 4299,
                  children: [
                    { label: '4.2.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r42992' },
                    { label: '4.2.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r42998' },
                    { label: '4.2.99.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r42999' },
                    { label: '4.2.99.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r429910' },
                    { label: '4.2.99.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r429911' },
                    { label: '4.2.99.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r429918' },
                    { label: '4.2.99.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r429920' },
                    { label: '4.2.99.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r429921' },
                    { label: '4.2.99.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r429922' },
                    { label: '4.2.99.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r429923' },
                    { label: '4.2.99.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r429924' },
                    { label: '4.2.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r4299-' }
                  ]
                }
              ]
            },
            {
              label: '4.3 Carbon-nitrogen lyases',
              idx: 43,
              children: [
                {
                  label: '4.3.1 Ammonia-lyases',
                  idx: 431,
                  children: [
                    { label: '4.3.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4311' },
                    { label: '4.3.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r4312' },
                    { label: '4.3.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r4313' },
                    { label: '4.3.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r4314' },
                    { label: '4.3.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r4315' },
                    { label: '4.3.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r4317' },
                    { label: '4.3.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r4319' },
                    { label: '4.3.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r43112' },
                    { label: '4.3.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r43114' },
                    { label: '4.3.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r43115' },
                    { label: '4.3.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r43116' },
                    { label: '4.3.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r43117' },
                    { label: '4.3.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r43118' },
                    { label: '4.3.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r43119' },
                    { label: '4.3.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r43123' },
                    { label: '4.3.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r43124' },
                    { label: '4.3.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r43125' },
                    { label: '4.3.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r43127' },
                    { label: '4.3.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r43128' },
                    { label: '4.3.1.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r43129' },
                    { label: '4.3.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r43130' },
                    { label: '4.3.1.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r43132' },
                    { label: '4.3.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r431-' }
                  ]
                },
                {
                  label: '4.3.2 Amidine-lyases',
                  idx: 432,
                  children: [
                    { label: '4.3.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4321' },
                    { label: '4.3.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r4322' },
                    { label: '4.3.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r4323' },
                    { label: '4.3.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r4325' },
                    { label: '4.3.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r4326' },
                    { label: '4.3.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r4327' },
                    { label: '4.3.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r4328' },
                    { label: '4.3.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r4329' },
                    { label: '4.3.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r43210' },
                    { label: '4.3.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r432-' }
                  ]
                },
                {
                  label: '4.3.3 Amine-lyases',
                  idx: 433,
                  children: [
                    { label: '4.3.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r4332' },
                    { label: '4.3.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r4335' },
                    { label: '4.3.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r4336' },
                    { label: '4.3.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r4337' },
                    { label: '4.3.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r433-' }
                  ]
                },
                {
                  label: '4.3.99 Other carbon-nitrogen lyases',
                  idx: 4399,
                  children: [
                    { label: '4.3.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r43991' },
                    { label: '4.3.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r43993' },
                    { label: '4.3.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r43994' },
                    { label: '4.3.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r4399-' }
                  ]
                }
              ]
            },
            {
              label: '4.4 Carbon-sulfur lyases',
              idx: 44,
              children: [
                {
                  label: '4.4.1 Carbon-sulfur lyases (only sub-subclass identified to date)',
                  idx: 441,
                  children: [
                    { label: '4.4.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4411' },
                    { label: '4.4.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r4412' },
                    { label: '4.4.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r4413' },
                    { label: '4.4.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r4414' },
                    { label: '4.4.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r4415' },
                    { label: '4.4.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r4418' },
                    { label: '4.4.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r44111' },
                    { label: '4.4.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r44113' },
                    { label: '4.4.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r44114' },
                    { label: '4.4.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r44115' },
                    { label: '4.4.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r44116' },
                    { label: '4.4.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r44117' },
                    { label: '4.4.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r44119' },
                    { label: '4.4.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r44120' },
                    { label: '4.4.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r44121' },
                    { label: '4.4.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r44122' },
                    { label: '4.4.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r44123' },
                    { label: '4.4.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r44124' },
                    { label: '4.4.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r44125' },
                    { label: '4.4.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r44126' },
                    { label: '4.4.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r44128' },
                    { label: '4.4.1.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r44134' },
                    { label: '4.4.1.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r44135' },
                    { label: '4.4.1.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r44137' },
                    { label: '4.4.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r441-' }
                  ]
                }
              ]
            },
            {
              label: '4.5 Carbon-halide lyases',
              idx: 45,
              children: [
                {
                  label: '4.5.1 Carbon-halide lyases (only sub-subclass identified to date)',
                  idx: 451,
                  children: [
                    { label: '4.5.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4511' },
                    { label: '4.5.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r4513' },
                    { label: '4.5.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r4515' },
                    { label: '4.5.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r451-' }
                  ]
                }
              ]
            },
            {
              label: '4.6 Phosphorus-oxygen lyases',
              idx: 46,
              children: [
                {
                  label: '4.6.1 Phosphorus-oxygen lyases (only sub-subclass identified to date)',
                  idx: 461,
                  children: [
                    { label: '4.6.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4611' },
                    { label: '4.6.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r4612' },
                    { label: '4.6.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r4613' },
                    { label: '4.6.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r4615' },
                    { label: '4.6.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r4616' },
                    { label: '4.6.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r46110' },
                    { label: '4.6.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r46112' },
                    { label: '4.6.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r46113' },
                    { label: '4.6.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r46114' },
                    { label: '4.6.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r46115' },
                    { label: '4.6.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r46116' },
                    { label: '4.6.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r46117' },
                    { label: '4.6.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r46118' },
                    { label: '4.6.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r46119' },
                    { label: '4.6.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r46120' },
                    { label: '4.6.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r46121' },
                    { label: '4.6.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r46122' },
                    { label: '4.6.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r46123' },
                    { label: '4.6.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r46124' },
                    { label: '4.6.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r461-' }
                  ]
                }
              ]
            },
            {
              label: '4.7 carbon-phosphorus lyases',
              idx: 47,
              children: [
                {
                  label: '4.7.1 carbon-phosphorus lyases (only sub-subclass identified to date)',
                  idx: 471,
                  children: [
                    { label: '4.7.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r4711' }
                  ]
                }
              ]
            },
            {
              label: '4.8 Nitrogen-oxygen lyases',
              idx: 48,
              children: [
                { label: '4.8.1 Hydro-lyases', idx: 481, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '4.98 ATP-independent chelatases',
              idx: 498,
              children: [
                { label: '4.98.1 Forming coordination complexes', idx: 4981, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '4.99 Other lyases',
              idx: 499,
              children: [
                {
                  label: '4.99.1 Sole sub-subclass for lyases that do not belong in the other subclasses',
                  idx: 4991,
                  children: [
                    { label: '4.99.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r49911' },
                    { label: '4.99.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r49912' },
                    { label: '4.99.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r49913' },
                    { label: '4.99.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r49914' },
                    { label: '4.99.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r49915' },
                    { label: '4.99.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r49916' },
                    { label: '4.99.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r49917' },
                    { label: '4.99.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r49918' },
                    { label: '4.99.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r49919' },
                    { label: '4.99.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r499110' },
                    { label: '4.99.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r499111' },
                    { label: '4.99.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r499112' }

                  ]
                }
              ]
            }
          ]
        },
        {
          label: '5. Isomerases',
          idx: 5,
          children: [
            {
              label: '5.1 Racemases and epimerases',
              idx: 51,
              children: [
                {
                  label: '5.1.1 Acting on amino acids and derivatives',
                  idx: 511,
                  children: [
                    { label: '5.1.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5111' },
                    { label: '5.1.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5112' },
                    { label: '5.1.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5113' },
                    { label: '5.1.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5114' },
                    { label: '5.1.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r5115' },
                    { label: '5.1.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r5117' },
                    { label: '5.1.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5118' },
                    { label: '5.1.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r51110' },
                    { label: '5.1.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r51111' },
                    { label: '5.1.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r51112' },
                    { label: '5.1.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r51113' },
                    { label: '5.1.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r51115' },
                    { label: '5.1.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r51116' },
                    { label: '5.1.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r51117' },
                    { label: '5.1.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r51118' },
                    { label: '5.1.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r51119' },
                    { label: '5.1.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r51120' },
                    { label: '5.1.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r51121' },
                    { label: '5.1.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r51122' },
                    { label: '5.1.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r51123' },
                    { label: '5.1.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r51124' },
                    { label: '5.1.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r511-' }

                  ]
                },
                {
                  label: '5.1.2 Acting on hydroxy acids and derivatives',
                  idx: 512,
                  children: [
                    { label: '5.1.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5121' },
                    { label: '5.1.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5122' },
                    { label: '5.1.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5123' },
                    { label: '5.1.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r5127' }

                  ]
                },
                {
                  label: '5.1.3 Acting on carbohydrates and derivatives',
                  idx: 513,
                  children: [
                    { label: '5.1.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5131' },
                    { label: '5.1.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5132' },
                    { label: '5.1.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5133' },
                    { label: '5.1.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r51310' },
                    { label: '5.1.3.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r51311' },
                    { label: '5.1.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r51313' },
                    { label: '5.1.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r51314' },
                    { label: '5.1.3.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r51315' },
                    { label: '5.1.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r51317' },
                    { label: '5.1.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r51318' },
                    { label: '5.1.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r51319' },
                    { label: '5.1.3.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r51320' },
                    { label: '5.1.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r51321' },
                    { label: '5.1.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r51322' },
                    { label: '5.1.3.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r51323' },
                    { label: '5.1.3.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r51324' },
                    { label: '5.1.3.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r51325' },
                    { label: '5.1.3.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r51326' },
                    { label: '5.1.3.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r51327' },
                    { label: '5.1.3.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r51329' },
                    { label: '5.1.3.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r51330' },
                    { label: '5.1.3.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r51331' },
                    { label: '5.1.3.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r51332' },
                    { label: '5.1.3.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r51333' },
                    { label: '5.1.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r513-' }

                  ]
                },
                {
                  label: '5.1.99 Acting on other compounds',
                  idx: 5199,
                  children: [
                    { label: '5.1.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r51991' },
                    { label: '5.1.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r51993' },
                    { label: '5.1.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r51994' },
                    { label: '5.1.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r51995' },
                    { label: '5.1.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r51996' },
                    { label: '5.1.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r51997' },
                    { label: '5.1.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r51998' },
                    { label: '5.1.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r5199-' }

                  ]
                }
              ]
            },
            {
              label: '5.2 cis-trans-Isomerases',
              idx: 52,
              children: [
                {
                  label: '5.2.1 cis-trans Isomerases (only sub-subclass identified to date)',
                  idx: 521,
                  children: [
                    { label: '5.2.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5211' },
                    { label: '5.2.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5212' },
                    { label: '5.2.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5214' },
                    { label: '5.2.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r5217' },
                    { label: '5.2.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5218' },
                    { label: '5.2.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r52112' },
                    { label: '5.2.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r52113' },
                    { label: '5.2.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r52114' },
                    { label: '5.2.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r521-' }

                  ]
                }
              ]
            },
            {
              label: '5.3 Intramolecular oxidoreductases',
              idx: 53,
              children: [
                {
                  label: '5.3.1 Interconverting aldoses and ketoses, and related compounds',
                  idx: 531,
                  children: [
                    { label: '5.3.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5311' },
                    { label: '5.3.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5313' },
                    { label: '5.3.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5314' },
                    { label: '5.3.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r53112' },
                    { label: '5.3.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r53113' },
                    { label: '5.3.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r53114' },
                    { label: '5.3.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r53115' },
                    { label: '5.3.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r53116' },
                    { label: '5.3.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r53117' },
                    { label: '5.3.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r53122' },
                    { label: '5.3.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r53123' },
                    { label: '5.3.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r53124' },
                    { label: '5.3.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r53125' },
                    { label: '5.3.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r53126' },
                    { label: '5.3.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r53127' },
                    { label: '5.3.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r53128' },
                    { label: '5.3.1.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r53129' },
                    { label: '5.3.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r53130' },
                    { label: '5.3.1.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r53131' },
                    { label: '5.3.1.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r53132' },
                    { label: '5.3.1.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r53133' },
                    { label: '5.3.1.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r53134' },
                    { label: '5.3.1.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r53135' },
                    { label: '5.3.1.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r53136' },
                    { label: '5.3.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r531-' }
                  ]
                },
                {
                  label: '5.3.2 Interconverting keto- and enol-groups',
                  idx: 532,
                  children: [
                    { label: '5.3.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5321' },
                    { label: '5.3.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5322' },
                    { label: '5.3.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5323' },
                    { label: '5.3.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r5325' },
                    { label: '5.3.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r5326' },
                    { label: '5.3.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5328' },
                    { label: '5.3.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r532-' }
                  ]
                },
                {
                  label: '5.3.3 Transposing C=C bonds',
                  idx: 533,
                  children: [
                    { label: '5.3.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5331' },
                    { label: '5.3.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5332' },
                    { label: '5.3.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5333' },
                    { label: '5.3.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5334' },
                    { label: '5.3.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r5335' },
                    { label: '5.3.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r5336' },
                    { label: '5.3.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r5337' },
                    { label: '5.3.3.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5338' },
                    { label: '5.3.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r53310' },
                    { label: '5.3.3.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r53312' },
                    { label: '5.3.3.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r53313' },
                    { label: '5.3.3.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r53314' },
                    { label: '5.3.3.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r53317' },
                    { label: '5.3.3.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r53318' },
                    { label: '5.3.3.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r53319' },
                    { label: '5.3.3.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r53321' },
                    { label: '5.3.3.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r53322' },
                    { label: '5.3.3.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r53323' },
                    { label: '5.3.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r533-' }
                  ]
                },
                {
                  label: '5.3.4 Transposing S-S bonds',
                  idx: 534,
                  children: [
                    { label: '5.3.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5341' }
                  ]
                },
                {
                  label: '5.3.99 Other intramolecular oxidoreductases',
                  idx: 5399,
                  children: [
                    { label: '5.3.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r53992' },
                    { label: '5.3.99.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r53993' },
                    { label: '5.3.99.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r53994' },
                    { label: '5.3.99.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r53995' },
                    { label: '5.3.99.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r53996' },
                    { label: '5.3.99.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r53997' },
                    { label: '5.3.99.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r53998' },
                    { label: '5.3.99.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r53999' },
                    { label: '5.3.99.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r539910' },
                    { label: '5.3.99.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r539911' }
                  ]
                }
              ]
            },
            {
              label: '5.4 Intramolecular transferases',
              idx: 54,
              children: [
                {
                  label: '5.4.1 Transferring acyl groups',
                  idx: 541,
                  children: [
                    { label: '5.4.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5412' },
                    { label: '5.4.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5413' },
                    { label: '5.4.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5414' }
                  ]
                },
                {
                  label: '5.4.2 Phosphotransferases (phosphomutases)',
                  idx: 542,
                  children: [
                    { label: '5.4.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5421' },
                    { label: '5.4.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5422' },
                    { label: '5.4.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5423' },
                    { label: '5.4.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5424' },
                    { label: '5.4.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r5426' },
                    { label: '5.4.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r5427' },
                    { label: '5.4.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5428' },
                    { label: '5.4.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r5429' },
                    { label: '5.4.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r54210' },
                    { label: '5.4.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r54211' },
                    { label: '5.4.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r54212' },
                    { label: '5.4.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r54213' },
                    { label: '5.4.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r542-' }
                  ]
                },
                {
                  label: '5.4.3 Transferring amino groups',
                  idx: 543,
                  children: [
                    { label: '5.4.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5431' },
                    { label: '5.4.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5432' },
                    { label: '5.4.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5433' },
                    { label: '5.4.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r5435' },
                    { label: '5.4.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r5436' },
                    { label: '5.4.3.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5438' },
                    { label: '5.4.3.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r5439' },
                    { label: '5.4.3.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r54310' },
                    { label: '5.4.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r543-' }
                  ]
                },
                {
                  label: '5.4.4 Transferring hydroxy groups',
                  idx: 544,
                  children: [
                    { label: '5.4.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5441' },
                    { label: '5.4.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5442' },
                    { label: '5.4.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5443' },
                    { label: '5.4.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5444' },
                    { label: '5.4.4.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r5445' },
                    { label: '5.4.4.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r5446' },
                    { label: '5.4.4.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r5447' },
                    { label: '5.4.4.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5448' }
                  ]
                },
                {
                  label: '5.4.99 Transferring other groups',
                  idx: 5499,
                  children: [
                    { label: '5.4.99.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r54991' },
                    { label: '5.4.99.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r54992' },
                    { label: '5.4.99.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r549911' },
                    { label: '5.4.99.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r549912' },
                    { label: '5.4.99.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r549913' },
                    { label: '5.4.99.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r549914' },
                    { label: '5.4.99.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r549915' },
                    { label: '5.4.99.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r549916' },
                    { label: '5.4.99.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r549917' },
                    { label: '5.4.99.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r549918' },
                    { label: '5.4.99.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r549919' },
                    { label: '5.4.99.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r549920' },
                    { label: '5.4.99.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r549921' },
                    { label: '5.4.99.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r549922' },
                    { label: '5.4.99.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r549923' },
                    { label: '5.4.99.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r549924' },
                    { label: '5.4.99.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r549925' },
                    { label: '5.4.99.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r549926' },
                    { label: '5.4.99.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r549927' },
                    { label: '5.4.99.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r549928' },
                    { label: '5.4.99.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r549929' },
                    { label: '5.4.99.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r549930' },
                    { label: '5.4.99.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r549931' },
                    { label: '5.4.99.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r549932' },
                    { label: '5.4.99.- ', children: [{ label: 'Select Enzyme' }], idx: 'r5499-' }
                  ]
                }
              ]
            },
            {
              label: '5.5 Intramolecular lyases',
              idx: 55,
              children: [
                {
                  label: '5.5.1 Intramolecular lyases (only sub-subclass identified to date)',
                  idx: 551,
                  children: [
                    { label: '5.5.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5511' },
                    { label: '5.5.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5512' },
                    { label: '5.5.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r5514' },
                    { label: '5.5.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r5515' },
                    { label: '5.5.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r5516' },
                    { label: '5.5.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r55112' },
                    { label: '5.5.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r55113' },
                    { label: '5.5.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r55114' },
                    { label: '5.5.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r55115' },
                    { label: '5.5.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r55116' },
                    { label: '5.5.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r55117' },
                    { label: '5.5.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r55118' },
                    { label: '5.5.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r55119' },
                    { label: '5.5.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r55120' },
                    { label: '5.5.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r55123' },
                    { label: '5.5.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r55124' },
                    { label: '5.5.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r55125' },
                    { label: '5.5.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r55126' },
                    { label: '5.5.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r55127' },
                    { label: '5.5.1.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r55128' },
                    { label: '5.5.1.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r55129' },
                    { label: '5.5.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r55130' },
                    { label: '5.5.1.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r55134' },
                    { label: '5.5.1.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r55135' },
                    { label: '5.5.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r551-' }

                  ]
                }
              ]
            },
            {
              label: '5.6 Isomerases altering macromolecular conformation',
              idx: 56,
              children: [
                {
                  label: '5.6.1 Enzymes altering polypeptide conformation or assembly',
                  idx: 561,
                  children: [
                    { label: '5.6.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5611' },
                    { label: '5.6.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r5616' },
                    { label: '5.6.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r5617' },
                    { label: '5.6.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r5618' }
                  ]
                },
                {
                  label: '5.6.2 Enzymes altering nucleic acid conformation',
                  idx: 562,
                  children: [
                    { label: '5.6.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r5621' },
                    { label: '5.6.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r5622' },
                    { label: '5.6.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r5623' }
                  ]
                }
              ]
            },
            {
              label: '5.99 Other isomerases',
              idx: 599,
              children: [
                {
                  label: '5.99.1 Sole sub-subclass for isomerases that do not belong in the other subclasses',
                  idx: 5991,
                  children: [
                    { label: '5.99.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r59912' },
                    { label: '5.99.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r59913' },
                    { label: '5.99.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r59914' },
                    { label: '5.99.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r5991-' }
                  ]
                }
              ]
            }
          ]
        },
        {
          label: '6. Ligases',
          idx: 6,
          children: [
            {
              label: '6.1 Forming carbon-oxygen bonds',
              idx: 61,
              children: [
                {
                  label: '6.1.1 Ligases forming aminoacyl-tRNA and related compounds',
                  idx: 611,
                  children: [
                    { label: '6.1.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6111' },
                    { label: '6.1.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6112' },
                    { label: '6.1.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6113' },
                    { label: '6.1.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r6114' },
                    { label: '6.1.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r6115' },
                    { label: '6.1.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r6116' },
                    { label: '6.1.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r6117' },
                    { label: '6.1.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r6119' },
                    { label: '6.1.1.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r61110' },
                    { label: '6.1.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r61111' },
                    { label: '6.1.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r61112' },
                    { label: '6.1.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r61113' },
                    { label: '6.1.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r61114' },
                    { label: '6.1.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r61115' },
                    { label: '6.1.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r61116' },
                    { label: '6.1.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r61117' },
                    { label: '6.1.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r61118' },
                    { label: '6.1.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r61119' },
                    { label: '6.1.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r61120' },
                    { label: '6.1.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r61121' },
                    { label: '6.1.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r61122' },
                    { label: '6.1.1.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r61123' },
                    { label: '6.1.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r61126' },
                    { label: '6.1.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r61127' },
                    { label: '6.1.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r611-' }
                  ]
                },
                {
                  label: '6.1.2 acid-alcohol ligases (ester synthases)',
                  idx: 612,
                  children: [
                    { label: '6.1.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6121' },
                    { label: '6.1.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6122' },
                    { label: '6.1.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r612-' }

                  ]
                },
                {
                  label: '6.1.3 Cyclo-ligases',
                  idx: 613,
                  children: [
                    { label: '6.1.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6131' }
                  ]
                }
              ]
            },
            {
              label: '6.2 Forming carbon-sulfur bonds',
              idx: 62,
              children: [
                {
                  label: '6.2.1 Acid-thiol ligases',
                  idx: 621,
                  children: [
                    { label: '6.2.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6211' },
                    { label: '6.2.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6212' },
                    { label: '6.2.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6213' },
                    { label: '6.2.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r62112' },
                    { label: '6.2.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r62113' },
                    { label: '6.2.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r62114' },
                    { label: '6.2.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r62115' },
                    { label: '6.2.1.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r62116' },
                    { label: '6.2.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r62117' },
                    { label: '6.2.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r62119' },
                    { label: '6.2.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r62120' },
                    { label: '6.2.1.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r62122' },
                    { label: '6.2.1.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r62124' },
                    { label: '6.2.1.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r62125' },
                    { label: '6.2.1.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r62126' },
                    { label: '6.2.1.27 ', children: [{ label: 'Select Enzyme' }], idx: 'r62127' },
                    { label: '6.2.1.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r62130' },
                    { label: '6.2.1.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r62132' },
                    { label: '6.2.1.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r62133' },
                    { label: '6.2.1.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r62134' },
                    { label: '6.2.1.35 ', children: [{ label: 'Select Enzyme' }], idx: 'r62135' },
                    { label: '6.2.1.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r62136' },
                    { label: '6.2.1.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r62137' },
                    { label: '6.2.1.39 ', children: [{ label: 'Select Enzyme' }], idx: 'r62139' },
                    { label: '6.2.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r621-' }
                  ]
                },
                { label: '6.2.2 Amide---thiol ligases', idx: 622, children: [{ label: 'Select enzyme' }] }
              ]
            },
            {
              label: '6.3 Forming carbon-nitrogen bonds',
              idx: 63,
              children: [
                {
                  label: '6.3.1 Acid—ammonia (or amine) ligases (amide synthases)',
                  idx: 631,
                  children: [
                    { label: '6.3.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6311' },
                    { label: '6.3.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6312' },
                    { label: '6.3.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r6315' },
                    { label: '6.3.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r6316' },
                    { label: '6.3.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r6318' },
                    { label: '6.3.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r6319' },
                    { label: '6.3.1.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r63111' },
                    { label: '6.3.1.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r63112' },
                    { label: '6.3.1.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r63113' },
                    { label: '6.3.1.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r63114' },
                    { label: '6.3.1.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r63115' },
                    { label: '6.3.1.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r63117' },
                    { label: '6.3.1.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r63118' },
                    { label: '6.3.1.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r63119' },
                    { label: '6.3.1.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r63120' },
                    { label: '6.3.1.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r63121' },
                    { label: '6.3.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r631-' }
                  ]
                },
                {
                  label: '6.3.2 Acid—amino-acid ligases (peptide synthases)',
                  idx: 632,
                  children: [
                    { label: '6.3.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6321' },
                    { label: '6.3.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6322' },
                    { label: '6.3.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6323' },
                    { label: '6.3.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r63210' },
                    { label: '6.3.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r63211' },
                    { label: '6.3.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r63212' },
                    { label: '6.3.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r63213' },
                    { label: '6.3.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r63214' },
                    { label: '6.3.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r63215' },
                    { label: '6.3.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r63217' },
                    { label: '6.3.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r63219' },
                    { label: '6.3.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r63220' },
                    { label: '6.3.2.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r63223' },
                    { label: '6.3.2.25 ', children: [{ label: 'Select Enzyme' }], idx: 'r63225' },
                    { label: '6.3.2.26 ', children: [{ label: 'Select Enzyme' }], idx: 'r63226' },
                    { label: '6.3.2.28 ', children: [{ label: 'Select Enzyme' }], idx: 'r63228' },
                    { label: '6.3.2.29 ', children: [{ label: 'Select Enzyme' }], idx: 'r63229' },
                    { label: '6.3.2.30 ', children: [{ label: 'Select Enzyme' }], idx: 'r63230' },
                    { label: '6.3.2.31 ', children: [{ label: 'Select Enzyme' }], idx: 'r63231' },
                    { label: '6.3.2.32 ', children: [{ label: 'Select Enzyme' }], idx: 'r63232' },
                    { label: '6.3.2.33 ', children: [{ label: 'Select Enzyme' }], idx: 'r63233' },
                    { label: '6.3.2.34 ', children: [{ label: 'Select Enzyme' }], idx: 'r63234' },
                    { label: '6.3.2.36 ', children: [{ label: 'Select Enzyme' }], idx: 'r63236' },
                    { label: '6.3.2.37 ', children: [{ label: 'Select Enzyme' }], idx: 'r63237' },
                    { label: '6.3.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r632-' }
                  ]
                },
                {
                  label: '6.3.3 Cyclo-ligases',
                  idx: 633,
                  children: [
                    { label: '6.3.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6331' },
                    { label: '6.3.3.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6332' },
                    { label: '6.3.3.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6333' },
                    { label: '6.3.3.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r6334' },
                    { label: '6.3.3.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r6335' },
                    { label: '6.3.3.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r6336' },
                    { label: '6.3.3.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r6337' },
                    { label: '6.3.3.- ', children: [{ label: 'Select Enzyme' }], idx: 'r633-' }
                  ]
                },
                {
                  label: '6.3.4 Other carbon-nitrogen ligases',
                  idx: 634,
                  children: [
                    { label: '6.3.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6342' },
                    { label: '6.3.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6343' },
                    { label: '6.3.4.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r6344' },
                    { label: '6.3.4.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r6345' },
                    { label: '6.3.4.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r6346' },
                    { label: '6.3.4.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r6349' },
                    { label: '6.3.4.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r63410' },
                    { label: '6.3.4.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r63411' },
                    { label: '6.3.4.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r63412' },
                    { label: '6.3.4.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r63413' },
                    { label: '6.3.4.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r63414' },
                    { label: '6.3.4.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r63415' },
                    { label: '6.3.4.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r63416' },
                    { label: '6.3.4.18 ', children: [{ label: 'Select Enzyme' }], idx: 'r63418' },
                    { label: '6.3.4.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r63419' },
                    { label: '6.3.4.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r63420' },
                    { label: '6.3.4.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r63421' },
                    { label: '6.3.4.22 ', children: [{ label: 'Select Enzyme' }], idx: 'r63422' },
                    { label: '6.3.4.23 ', children: [{ label: 'Select Enzyme' }], idx: 'r63423' },
                    { label: '6.3.4.24 ', children: [{ label: 'Select Enzyme' }], idx: 'r63424' },
                    { label: '6.3.4.- ', children: [{ label: 'Select Enzyme' }], idx: 'r634-' }
                  ]
                },
                {
                  label: '6.3.5 Carbon-nitrogen ligases with glutamine as amido-N-donor',
                  idx: 635,
                  children: [
                    { label: '6.3.5.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6351' },
                    { label: '6.3.5.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6352' },
                    { label: '6.3.5.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6353' },
                    { label: '6.3.5.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r6354' },
                    { label: '6.3.5.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r6355' },
                    { label: '6.3.5.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r6357' },
                    { label: '6.3.5.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r6359' },
                    { label: '6.3.5.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r63510' },
                    { label: '6.3.5.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r63511' },
                    { label: '6.3.5.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r63512' },
                    { label: '6.3.5.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r63513' },
                    { label: '6.3.5.- ', children: [{ label: 'Select Enzyme' }], idx: 'r635-' }
                  ]
                }
              ]
            },
            {
              label: '6.4 Forming carbon-carbon bonds',
              idx: 64,
              children: [
                {
                  label: '6.4.1 Ligases that form carbon-carbon bonds (only sub-subclass identified to date)',
                  idx: 641,
                  children: [
                    { label: '6.4.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6411' },
                    { label: '6.4.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6412' },
                    { label: '6.4.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6413' },
                    { label: '6.4.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r6414' },
                    { label: '6.4.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r6416' },
                    { label: '6.4.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r6417' },
                    { label: '6.4.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r6418' },
                    { label: '6.4.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r6419' },
                    { label: '6.4.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r641-' }
                  ]
                }
              ]
            },
            {
              label: '6.5 Forming phosphoric-ester bonds',
              idx: 65,
              children: [
                {
                  label: '6.5.1 Ligases that form phosphoric-ester bonds (only sub-subclass identified to date)',
                  idx: 651,
                  children: [
                    { label: '6.5.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6511' },
                    { label: '6.5.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6512' },
                    { label: '6.5.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r6513' },
                    { label: '6.5.1.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r6514' },
                    { label: '6.5.1.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r6515' },
                    { label: '6.5.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r6516' },
                    { label: '6.5.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r6517' },
                    { label: '6.5.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r6518' },
                    { label: '6.5.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r6519' },
                    { label: '6.5.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r651-' }
                  ]
                }
              ]
            },
            {
              label: '6.6 Forming nitrogen—metal bonds',
              idx: 66,
              children: [
                {
                  label: '6.6.1 Forming coordination complexes',
                  idx: 661,
                  children: [
                    { label: '6.6.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r6611' },
                    { label: '6.6.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r6612' }

                  ]
                }
              ]
            },
            {
              label: '6.7 Forming nitrogen-nitrogen bonds',
              idx: 67,
              children: [
                { label: '6.7.1 Forming diazo bonds', idx: 671, children: [{ label: 'Select enzyme' }] }
              ]
            }
          ]
        },
        {
          label: '7. Translocases',
          idx: 7,
          children: [
            {
              label: '7.1 Catalysing the translocation of hydrons',
              idx: 71,
              children: [
                {
                  label: '7.1.1 Linked to oxidoreductase reactions',
                  idx: 711,
                  children: [
                    { label: '7.1.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7111' },
                    { label: '7.1.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r7112' },
                    { label: '7.1.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r7113' },
                    { label: '7.1.1.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r7116' },
                    { label: '7.1.1.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r7117' },
                    { label: '7.1.1.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r7118' },
                    { label: '7.1.1.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r7119' },
                    { label: '7.1.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r711-' }
                  ]
                },
                {
                  label: '7.1.2 Linked to the hydrolysis of a nucleoside triphosphate',
                  idx: 712,
                  children: [
                    { label: '7.1.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7121' },
                    { label: '7.1.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r7122' }
                  ]
                },
                {
                  label: ' 7.1.3 Linked to the hydrolysis of diphosphate',
                  idx: 713,
                  children: [
                    { label: '7.1.3.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7131' }
                  ]
                }
              ]
            },
            {
              label: '7.2 Catalysing the translocation of inorganic cations',
              idx: 72,
              children: [
                {
                  label: '7.2.1 Linked to oxidoreductase reactions',
                  idx: 721,
                  children: [
                    { label: '7.2.1.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7211' },
                    { label: '7.2.1.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r7212' },
                    { label: '7.2.1.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r7213' },
                    { label: '7.2.1.- ', children: [{ label: 'Select Enzyme' }], idx: 'r721-' }
                  ]
                },
                {
                  label: '7.2.2 Linked to the hydrolysis of a nucleoside triphosphate',
                  idx: 722,
                  children: [
                    { label: '7.2.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7221' },
                    { label: '7.2.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r7222' },
                    { label: '7.2.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r7223' },
                    { label: '7.2.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r7224' },
                    { label: '7.2.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r7225' },
                    { label: '7.2.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r7226' },
                    { label: '7.2.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r7227' },
                    { label: '7.2.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r7228' },
                    { label: '7.2.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r7229' },
                    { label: '7.2.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r72210' },
                    { label: '7.2.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r72211' },
                    { label: '7.2.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r72212' },
                    { label: '7.2.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r72213' },
                    { label: '7.2.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r72214' },
                    { label: '7.2.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r72215' },
                    { label: '7.2.2.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r72216' },
                    { label: '7.2.2.17 ', children: [{ label: 'Select Enzyme' }], idx: 'r72217' },
                    { label: '7.2.2.19 ', children: [{ label: 'Select Enzyme' }], idx: 'r72219' },
                    { label: '7.2.2.20 ', children: [{ label: 'Select Enzyme' }], idx: 'r72220' },
                    { label: '7.2.2.21 ', children: [{ label: 'Select Enzyme' }], idx: 'r72221' },
                    { label: '7.2.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r722-' }
                  ]
                },
                {
                  label: '7.2.4 Linked to decarboxylation',
                  idx: 724,
                  children: [
                    { label: '7.2.4.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7241' },
                    { label: '7.2.4.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r7242' },
                    { label: '7.2.4.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r7243' },
                    { label: '7.2.4.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r7245' }
                  ]
                }
              ]
            },
            {
              label: '7.3 Catalysing the translocation of inorganic anions and their chelates',
              idx: 73,
              children: [
                {
                  label: '7.3.2 Linked to the hydrolysis of a nucleoside triphosphate',
                  idx: 732,
                  children: [
                    { label: '7.3.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7321' },
                    { label: '7.3.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r7322' },
                    { label: '7.3.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r7323' },
                    { label: '7.3.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r7324' },
                    { label: '7.3.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r7325' },
                    { label: '7.3.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r7326' },
                    { label: '7.3.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r7327' },
                    { label: '7.3.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r732-' }
                  ]
                }
              ]
            },
            {
              label: '7.4 Catalysing the translocation of amino acids and peptides',
              idx: 74,
              children: [
                {
                  label: '7.4.2 Linked to the hydrolysis of a nucleoside triphosphate',
                  idx: 742,
                  children: [
                    { label: '7.4.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7421' },
                    { label: '7.4.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r7424' },
                    { label: '7.4.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r7425' },
                    { label: '7.4.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r7426' },
                    { label: '7.4.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r7427' },
                    { label: '7.4.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r7428' },
                    { label: '7.4.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r7429' },
                    { label: '7.4.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r74210' },
                    { label: '7.4.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r74211' },
                    { label: '7.4.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r74212' },
                    { label: '7.4.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r742-' }
                  ]
                }
              ]
            },
            {
              label: '7.5 Catalysing the translocation of carbohydrates and their derivatives',
              idx: 75,
              children: [
                {
                  label: '7.5.2 Linked to the hydrolysis of a nucleoside triphosphate',
                  idx: 752,
                  children: [
                    { label: '7.5.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7521' },
                    { label: '7.5.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r7523' },
                    { label: '7.5.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r7524' },
                    { label: '7.5.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r7525' },
                    { label: '7.5.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r7526' },
                    { label: '7.5.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r7527' },
                    { label: '7.5.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r7528' },
                    { label: '7.5.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r7529' },
                    { label: '7.5.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r75210' },
                    { label: '7.5.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r75211' },
                    { label: '7.5.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r75212' },
                    { label: '7.5.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r75213' },
                    { label: '7.5.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r752-' }
                  ]
                }
              ]
            },
            {
              label: '7.6 Catalysing the translocation of other compounds',
              idx: 76,
              children: [
                {
                  label: '7.6.2 Linked to the hydrolysis of a nucleoside triphosphate',
                  idx: 762,
                  children: [
                    { label: '7.6.2.1 ', children: [{ label: 'Select Enzyme' }], idx: 'r7621' },
                    { label: '7.6.2.2 ', children: [{ label: 'Select Enzyme' }], idx: 'r7622' },
                    { label: '7.6.2.3 ', children: [{ label: 'Select Enzyme' }], idx: 'r7623' },
                    { label: '7.6.2.4 ', children: [{ label: 'Select Enzyme' }], idx: 'r7624' },
                    { label: '7.6.2.5 ', children: [{ label: 'Select Enzyme' }], idx: 'r7625' },
                    { label: '7.6.2.6 ', children: [{ label: 'Select Enzyme' }], idx: 'r7626' },
                    { label: '7.6.2.7 ', children: [{ label: 'Select Enzyme' }], idx: 'r7627' },
                    { label: '7.6.2.8 ', children: [{ label: 'Select Enzyme' }], idx: 'r7628' },
                    { label: '7.6.2.9 ', children: [{ label: 'Select Enzyme' }], idx: 'r7629' },
                    { label: '7.6.2.10 ', children: [{ label: 'Select Enzyme' }], idx: 'r76210' },
                    { label: '7.6.2.11 ', children: [{ label: 'Select Enzyme' }], idx: 'r76211' },
                    { label: '7.6.2.12 ', children: [{ label: 'Select Enzyme' }], idx: 'r76212' },
                    { label: '7.6.2.13 ', children: [{ label: 'Select Enzyme' }], idx: 'r76213' },
                    { label: '7.6.2.14 ', children: [{ label: 'Select Enzyme' }], idx: 'r76214' },
                    { label: '7.6.2.15 ', children: [{ label: 'Select Enzyme' }], idx: 'r76215' },
                    { label: '7.6.2.16 ', children: [{ label: 'Select Enzyme' }], idx: 'r76216' },
                    { label: '7.6.2.- ', children: [{ label: 'Select Enzyme' }], idx: 'r762-' }
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  },

  setup () {
    return {
      splitterModel: ref(50),
      selected: ref('')
      // simple: [
      //   {
      //     label: '1. Oxidoreductases',
      //     idx: 0,
      //     children: [
      //       {
      //         label: '1.1 Acting on the CH-OH group of donors',
      //         idx: 0,
      //         children: [
      //           {
      //             label: '1.1.1 With NAD+ or NADP+ as acceptor',
      //             idx: 0,
      //             children: [
      //               {
      //                 label: this.chosen_enzyme
      //               }
      //             ]
      //           },
      //           { label: '1.1.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.1.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.1.4 With a disulfide as acceptor', idx: 3 },
      //           { label: '1.1.5 With a quinone or similar compound as acceptor', idx: 4 },
      //           { label: '1.1.7 With an iron-sulfur protein as acceptor', idx: 5 },
      //           { label: '1.1.9 With a copper protein as acceptor', idx: 6 },
      //           { label: '1.1.98 With other, known, physiological acceptors', idx: 7 },
      //           { label: '1.1.99 With unknown physiological acceptors', idx: 8 }
      //         ]
      //       },
      //       {
      //         label: '1.2 Acting on the aldehyde or oxo group of donors',
      //         idx: 1,
      //         children: [
      //           { label: '1.2.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.2.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.2.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.2.4 With a disulfide as acceptor', idx: 3 },
      //           { label: '1.2.5 With a quinone or similar compound as acceptor', idx: 4 },
      //           { label: '1.2.7 With an iron-sulfur protein as acceptor', idx: 5 },
      //           { label: '1.2.98. undefined', idx: 6 },
      //           { label: '1.2.99 With unknown physiological acceptors', idx: 7 }
      //         ]
      //       },
      //       {
      //         label: '1.3 Acting on the CH-CH group of donors',
      //         idx: 2,
      //         children: [
      //           { label: '1.3.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.3.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.3.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.3.4 With a disulfide as acceptor', idx: 3 },
      //           { label: '1.3.5 With a quinone or related compound as acceptor', idx: 4 },
      //           { label: '1.3.7 With an iron-sulfur protein as acceptor', idx: 5 },
      //           { label: '1.3.8 With a flavin as acceptor', idx: 6 },
      //           { label: '1.3.98 With other, known, physiological acceptors', idx: 7 },
      //           { label: '1.3.99 With unknown physiological acceptors', idx: 8 }
      //         ]
      //       },
      //       {
      //         label: '1.4 Acting on the CH-NH2 group of donors',
      //         idx: 3,
      //         children: [
      //           { label: '1.4.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.4.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.4.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.4.4 With a disulfide as acceptor', idx: 3 },
      //           { label: '1.4.5 With a quinone or other compound as acceptor', idx: 4 },
      //           { label: '1.4.7 With an iron-sulfur protein as acceptor', idx: 5 },
      //           { label: '1.4.9 With a copper protein as acceptor', idx: 6 },
      //           { label: '1.4.98. undefined', idx: 7 },
      //           { label: '1.4.99 With unknown physiological acceptors', idx: 8 }
      //         ]
      //       },
      //       {
      //         label: '1.5 Acting on the CH-NH group of donors',
      //         idx: 4,
      //         children: [
      //           { label: '1.5.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.5.3 With oxygen as acceptor', idx: 1 },
      //           { label: '1.5.4 With a disulfide as acceptor', idx: 2 },
      //           { label: '1.5.5 With a quinone or similar compound as acceptor', idx: 3 },
      //           { label: '1.5.7 With an iron-sulfur protein as acceptor', idx: 4 },
      //           { label: '1.5.8 With a flavin or flavoprotein as acceptor', idx: 5 },
      //           { label: '1.5.98 With other, known, physiological acceptors', idx: 6 },
      //           { label: '1.5.99 With unknown physiological acceptors', idx: 7 }
      //         ]
      //       },
      //       {
      //         label: '1.6 Acting on NADH or NADPH',
      //         idx: 5,
      //         children: [
      //           { label: '1.6.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.6.2 With a heme protein as acceptor', idx: 1 },
      //           { label: '1.6.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.6.4 With a disulfide as acceptor (deleted sub-subclass)', idx: 3 },
      //           { label: '1.6.5 With a quinone or similar compound as acceptor', idx: 4 },
      //           { label: '1.6.6 With a nitrogenous group as acceptor', idx: 5 },
      //           { label: '1.6.7 With an iron-sulfur protein as acceptor (deleted sub-subclass)', idx: 6 },
      //           { label: '1.6.8 With a flavin as acceptor (deleted sub-subclass)', idx: 7 },
      //           { label: '1.6.99 With unknown physiological acceptors', idx: 8 }
      //         ]
      //       },
      //       {
      //         label: '1.7 Acting on other nitrogenous compounds as donors',
      //         idx: 6,
      //         children: [
      //           { label: '1.7.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.7.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.7.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.7.5 With a quinone or similar compound as acceptor', idx: 3 },
      //           { label: '1.7.6 With a nitrogenous group as acceptor', idx: 4 },
      //           { label: '1.7.7 With an iron-sulfur protein as acceptor', idx: 5 },
      //           { label: '1.7.9 With a copper protein as acceptor', idx: 6 },
      //           { label: '1.7.99 With unknown physiological acceptors', idx: 7 }
      //         ]
      //       },
      //       {
      //         label: '1.8 Acting on a sulfur group of donors',
      //         idx: 7,
      //         children: [
      //           { label: '1.8.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.8.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.8.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.8.4 With a disulfide as acceptor', idx: 3 },
      //           { label: '1.8.5 With a quinone or similar compound as acceptor', idx: 4 },
      //           { label: '1.8.6 With a nitrogenous group as acceptor (deleted sub-subclass)', idx: 5 },
      //           { label: '1.8.7 With an iron-sulfur protein as acceptor', idx: 6 },
      //           { label: '1.8.98 With other, known, physiological acceptors', idx: 7 },
      //           { label: '1.8.99 With unknown physiological acceptors', idx: 8 }

      //         ]
      //       },
      //       {
      //         label: '1.9 Acting on a heme group of donors',
      //         idx: 8,
      //         children: [
      //           { label: '1.9.3 With oxygen as acceptor', idx: 0 },
      //           { label: '1.9.6 With a nitrogenous group as acceptor', idx: 1 },
      //           { label: '1.9.98 With other, known, physiological acceptors', idx: 2 },
      //           { label: '1.9.99 With unknown physiological acceptors', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '1.10 Acting on diphenols and related substances as donors',
      //         idx: 9,
      //         children: [
      //           { label: '1.10.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.10.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.10.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.10.5 With a quinone or related compound as acceptor', idx: 3 },
      //           { label: '1.10.9 With a copper protein as acceptor', idx: 4 },
      //           { label: '1.10.99 With unknown physiological acceptors', idx: 5 }
      //         ]
      //       },
      //       {
      //         label: '1.11 Acting on a peroxide as acceptor',
      //         idx: 10,
      //         children: [
      //           { label: '1.11.1 Peroxidases', idx: 0 },
      //           { label: '1.11.2 Peroxygenases', idx: 1 }
      //         ]
      //       },
      //       {
      //         label: '1.12 Acting on hydrogen as donor',
      //         idx: 11,
      //         children: [
      //           { label: '1.12.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.12.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.12.5 With a quinone or similar compound as acceptor', idx: 2 },
      //           { label: '1.12.7 With an iron-sulfur protein as acceptor', idx: 3 },
      //           { label: '1.12.98 With other, known, physiological acceptors', idx: 4 },
      //           { label: '1.12.99 With unknown physiological acceptors', idx: 5 }
      //         ]
      //       },
      //       {
      //         label: '1.13 Acting on single donors with incorporation of molecular oxygen (oxygenases)',
      //         idx: 12,
      //         children: [
      //           { label: '1.13.1. undefined', idx: 0 },
      //           { label: '1.13.11 With incorporation of two atoms of oxygen', idx: 1 },
      //           { label: '1.13.12 With incorporation of one atom of oxygen (internal monooxygenases or internal mixed-function oxidases)', idx: 2 },
      //           { label: '1.13.99 Miscellaneous', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '1.14 Acting on paired donors, with incorporation or reduction of molecular oxygen',
      //         idx: 13,
      //         children: [
      //           { label: '1.14.1 With NADH or NADPH as one donor (deleted sub-subclass)', idx: 0 },
      //           { label: '1.14.2 With ascorbate as one donor (deleted sub-subclass)', idx: 1 },
      //           { label: '1.14.3 With reduced pteridine as one donor (deleted sub-subclass)', idx: 2 },
      //           { label: '1.14.11 With 2-oxoglutarate as one donor, and incorporation of one atom of oxygen into each donor', idx: 3 },
      //           { label: '1.14.12 With NADH or NADPH as one donor, and incorporation of two atoms of oxygen into the other donor', idx: 4 },
      //           { label: '1.14.13 With NADH or NADPH as one donor, and incorporation of one atom of oxygen into the other donor', idx: 5 },
      //           { label: '1.14.14 With reduced flavin or flavoprotein as one donor, and incorporation of one atom of oxygen into the other donor', idx: 6 },
      //           { label: '1.14.15 With reduced iron-sulfur protein as one donor, and incorporation of one atom of oxygen into the other donor', idx: 7 },
      //           { label: '1.14.16 With reduced pteridine as one donor, and incorporation of one atom of oxygen into the other donor', idx: 8 },
      //           { label: '1.14.17 With reduced ascorbate as one donor, and incorporation of one atom of oxygen into the other donor', idx: 9 },
      //           { label: '1.14.18 With another compound as one donor, and incorporation of one atom of oxygen into the other donor', idx: 10 },
      //           { label: '1.14.19 With oxidation of a pair of donors resulting in the reduction of O2 to two molecules of water', idx: 11 },
      //           { label: '1.14.20 With 2-oxoglutarate as one donor, and the other dehydrogenated', idx: 12 },
      //           { label: '1.14.21 With NADH or NADPH as one donor, and the other dehydrogenated', idx: 13 },
      //           { label: '1.14.99 Miscellaneous', idx: 14 }
      //         ]
      //       },
      //       {
      //         label: '1.15 Acting on superoxide as acceptor',
      //         idx: 14,
      //         children: [
      //           { label: '1.15.1 Acting on superoxide as acceptor (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '1.16 Oxidizing metal ions',
      //         idx: 15,
      //         children: [
      //           { label: '1.16.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.16.3 With oxygen as acceptor', idx: 1 },
      //           { label: '1.16.5 With a quinone or similar compound as acceptor', idx: 2 },
      //           { label: '1.16.8 With a flavin as acceptor', idx: 3 },
      //           { label: '1.16.9 With a copper protein as acceptor', idx: 4 },
      //           { label: '1.16.98 With other, known, physiological acceptors', idx: 5 },
      //           { label: '1.16.99 With unknown physiological acceptors', idx: 6 }
      //         ]
      //       },
      //       {
      //         label: '1.17 Acting on CH or CH2 groups',
      //         idx: 16,
      //         children: [
      //           { label: '1.17.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.17.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.17.3 With oxygen as acceptor', idx: 2 },
      //           { label: '1.17.4 With a disulfide as acceptor', idx: 3 },
      //           { label: '1.17.5 With a quinone or similar compound as acceptor', idx: 4 },
      //           { label: '1.17.7 With an iron-sulfur protein as acceptor', idx: 5 },
      //           { label: '1.17.8 With a flavin as acceptor', idx: 6 },
      //           { label: '1.17.9. undefined', idx: 7 },
      //           { label: '1.17.98 With other, known, physiological acceptors', idx: 8 },
      //           { label: '1.17.99 With unknown physiological acceptors', idx: 9 }
      //         ]
      //       },
      //       {
      //         label: '1.18 Acting on iron-sulfur proteins as donors',
      //         idx: 17,
      //         children: [
      //           { label: '1.18.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.18.2 With dinitrogen as acceptor (deleted sub-subclass)', idx: 1 },
      //           { label: '1.18.3 With H+ as acceptor (deleted sub-subclass)', idx: 2 },
      //           { label: '1.18.6 With dinitrogen as acceptor', idx: 3 },
      //           { label: '1.18.96 With other, known, acceptors (deleted sub-subclass)', idx: 4 },
      //           { label: '1.18.99 With H+ as acceptor (deleted sub-subclass)', idx: 5 }
      //         ]
      //       },
      //       {
      //         label: '1.19 Acting on reduced flavodoxin as donor',
      //         idx: 18,
      //         children: [
      //           { label: '1.19.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.19.6 With dinitrogen as acceptor', idx: 1 }
      //         ]
      //       },
      //       {
      //         label: '1.20 Acting on phosphorus or arsenic in donors',
      //         idx: 19,
      //         children: [
      //           { label: '1.20.1 With NAD+ or NADP+ as acceptor', idx: 0 },
      //           { label: '1.20.2 With a cytochrome as acceptor', idx: 1 },
      //           { label: '1.20.4 With disulfide as acceptor', idx: 2 },
      //           { label: '1.20.9 With a copper protein as acceptor', idx: 3 },
      //           { label: '1.20.98 With other, known, physiological acceptors', idx: 4 },
      //           { label: '1.20.99 With unknown physiological acceptors', idx: 5 }
      //         ]
      //       },
      //       {
      //         label: '1.21 Catalysing the reaction X-H + Y-H = X-Y',
      //         idx: 20,
      //         children: [
      //           { label: '1.21.1. undefined', idx: 0 },
      //           { label: '1.21.3 With oxygen as acceptor', idx: 1 },
      //           { label: '1.21.4 With a disulfide as acceptor', idx: 2 },
      //           { label: '1.21.98 With other, known, physiological acceptors', idx: 3 },
      //           { label: '1.21.99 With unknown physiological acceptors', idx: 4 }
      //         ]
      //       },
      //       {
      //         label: '1.22 Acting on halogen in donors',
      //         idx: 21,
      //         children: [
      //           { label: '1.22.1 With NAD+ or NADP+ as acceptor', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '1.23 Reducing C-O-C group as acceptor',
      //         idx: 22,
      //         children: [
      //           { label: '1.23.1 With NADH or NADPH as donor', idx: 0 },
      //           { label: '1.23.5 With a quinone or similar compound as acceptor', idx: 1 }
      //         ]
      //       },
      //       {
      //         label: '1.97 Other oxidoreductases',
      //         idx: 23,
      //         children: [
      //           { label: '1.97.1 Sole sub-subclass for oxidoreductases that do not belong in the other subclasses', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '1.98 Enzymes using H2 as reductant (deleted subclass)',
      //         idx: 24,
      //         children: [
      //           { label: '1.98.1. undefined', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '1.99 Other enzymes using O2 as oxidant (deleted subclass)',
      //         idx: 25,
      //         children: [
      //           { label: '1.99.1 Hydroxylases (now covered by EC 1.14)', idx: 0 },
      //           { label: '1.99.2 Oxygenases (now covered by EC 1.13)', idx: 1 }
      //         ]
      //       }
      //     ]
      //   },
      //   {
      //     label: '2. Transferases',
      //     idx: 1,
      //     children: [
      //       {
      //         label: '2.1 Transferring one-carbon groups',
      //         idx: 0,
      //         children: [
      //           { label: '2.1.1 Methyltransferases', idx: 0 },
      //           { label: '2.1.2 Hydroxymethyl-, formyl- and related transferases', idx: 1 },
      //           { label: '2.1.3 Carboxy- and carbamoyltransferases', idx: 2 },
      //           { label: '2.1.4 Amidinotransferases', idx: 3 },
      //           { label: '2.1.5 Methylenetransferases', idx: 4 }
      //         ]
      //       },
      //       {
      //         label: '2.2 Transferring aldehyde or ketonic groups',
      //         idx: 1,
      //         children: [
      //           { label: '2.2.1 Transketolases and transaldolases', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '2.3 Acyltransferases',
      //         idx: 2,
      //         children: [
      //           { label: '2.3.1 Transferring groups other than aminoacyl groups', idx: 0 },
      //           { label: '2.3.2 Aminoacyltransferases', idx: 1 },
      //           { label: '2.3.3 Acyl groups converted into alkyl groups on transfer', idx: 2 }
      //         ]
      //       },
      //       {
      //         label: '2.4 Glycosyltransferases',
      //         idx: 3,
      //         children: [
      //           { label: '2.4.1 Hexosyltransferases', idx: 0 },
      //           { label: '2.4.2 Pentosyltransferases', idx: 1 },
      //           { label: '2.4.3 Sialyltransferases', idx: 2 },
      //           { label: '2.4.99 Transferring other glycosyl groups', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '2.5 Transferring alkyl or aryl groups, other than methyl groups',
      //         idx: 4,
      //         children: [
      //           { label: '2.5.1 Transferring alkyl or aryl groups, other than methyl groups (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '2.6 Transferring nitrogenous groups',
      //         idx: 5,
      //         children: [
      //           { label: '2.6.1 Transaminases', idx: 0 },
      //           { label: '2.6.2 Amidinotransferases (deleted sub-subclass)', idx: 1 },
      //           { label: '2.6.3 Oximinotransferases', idx: 2 },
      //           { label: '2.6.99 Transferring other nitrogenous groups', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '2.7 Transferring phosphorus-containing groups',
      //         idx: 6,
      //         children: [
      //           { label: '2.7.1 Phosphotransferases with an alcohol group as acceptor', idx: 0 },
      //           { label: '2.7.2 Phosphotransferases with a carboxy group as acceptor', idx: 1 },
      //           { label: '2.7.3 Phosphotransferases with a nitrogenous group as acceptor', idx: 2 },
      //           { label: '2.7.4 Phosphotransferases with a phosphate group as acceptor', idx: 3 },
      //           { label: '2.7.5 Phosphotransferases with regeneration of donors, apparently catalysing intramolecular transfers (deleted sub-subclass)', idx: 4 },
      //           { label: '2.7.6 Diphosphotransferases', idx: 5 },
      //           { label: '2.7.7 Nucleotidyltransferases', idx: 6 },
      //           { label: '2.7.8 Transferases for other substituted phosphate groups', idx: 7 },
      //           { label: '2.7.9 Phosphotransferases with paired acceptors', idx: 8 },
      //           { label: '2.7.10 Protein-tyrosine kinases', idx: 9 },
      //           { label: '2.7.11 Protein-serine/threonine kinases', idx: 10 },
      //           { label: '2.7.12 Dual-specificity kinases (those acting on Ser/Thr and Tyr residues)', idx: 11 },
      //           { label: '2.7.13 Protein-histidine kinases', idx: 12 },
      //           { label: '2.7.14 Protein-arginine kinases', idx: 13 },
      //           { label: '2.7.99 Other protein kinases', idx: 14 }
      //         ]
      //       },
      //       {
      //         label: '2.8 Transferring sulfur-containing groups',
      //         idx: 7,
      //         children: [
      //           { label: '2.8.1 Sulfurtransferases', idx: 0 },
      //           { label: '2.8.2 Sulfotransferases', idx: 1 },
      //           { label: '2.8.3 CoA-transferases', idx: 2 },
      //           { label: '2.8.4 Transferring alkylthio groups', idx: 3 },
      //           { label: '2.8.5 Thiosulfotransferases', idx: 4 }
      //         ]
      //       },
      //       {
      //         label: '2.9 Transferring selenium-containing groups',
      //         idx: 8,
      //         children: [
      //           { label: '2.9.1 Selenotransferases', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '2.10 Transferring molybdenum- or tungsten-containing groups',
      //         idx: 9,
      //         children: [
      //           { label: '2.10.1 Molybdenumtransferases or tungstentransferases with sulfide groups as acceptors', idx: 0 }
      //         ]
      //       }
      //     ]
      //   },
      //   {
      //     label: '3. Hydrolases',
      //     idx: 2,
      //     children: [
      //       {
      //         label: '3.1 Acting on ester bonds',
      //         idx: 0,
      //         children: [
      //           { label: '3.1.1 Carboxylic-ester hydrolases', idx: 0 },
      //           { label: '3.1.2 Thioester hydrolases', idx: 1 },
      //           { label: '3.1.3 Phosphoric-monoester hydrolases', idx: 2 },
      //           { label: '3.1.4 Phosphoric-diester hydrolases', idx: 3 },
      //           { label: '3.1.5 Triphosphoric-monoester hydrolases', idx: 4 },
      //           { label: '3.1.6 Sulfuric-ester hydrolases', idx: 5 },
      //           { label: '3.1.7 Diphosphoric-monoester hydrolases', idx: 6 },
      //           { label: '3.1.8 Phosphoric-triester hydrolases', idx: 7 },
      //           { label: '3.1.11 Exodeoxyribonucleases producing 5′-phosphomonoesters', idx: 8 },
      //           { label: '3.1.12 Exodeoxyribonucleases producing 3′-phosphomonoesters', idx: 9 },
      //           { label: '3.1.13 Exoribonucleases producing 5′-phosphomonoesters', idx: 10 },
      //           { label: '3.1.14 Exoribonucleases producing 3\'-phosphomonoesters', idx: 11 },
      //           { label: '3.1.15 Exonucleases that are active with either ribo- or deoxyribonucleic acids and produce 5\' - phosphomonoesters', idx: 12 },
      //           { label: '3.1.16 Exonucleases that are active with either ribo- or deoxyribonucleic acids and produce 3\' - phosphomonoesters', idx: 13 },
      //           { label: '3.1.21 Endodeoxyribonucleases producing 5\' - phosphomonoesters', idx: 14 },
      //           { label: '3.1.22 Endodeoxyribonucleases producing 3\' - phosphomonoesters', idx: 15 },
      //           { label: '3.1.23 Site-specific endodeoxyribonucleases: cleavage is sequence specific (deleted sub-subclass)', idx: 16 },
      //           { label: '3.1.24 Site specific endodeoxyribonucleases: cleavage is not sequence specific (deleted sub-subclass)', idx: 17 },
      //           { label: '3.1.25 Site-specific endodeoxyribonucleases that are specific for altered bases', idx: 18 },
      //           { label: '3.1.26 Endoribonucleases producing 5\' - phosphomonoesters', idx: 19 },
      //           { label: '3.1.27 Endoribonucleases producing 3\' - phosphomonoesters', idx: 20 },
      //           { label: '3.1.30 Endoribonucleases that are active with either ribo- or deoxyribonucleic acids and produce 5\' - phosphomonoesters', idx: 21 },
      //           { label: '3.1.31 Endoribonucleases that are active with either ribo- or deoxyribonucleic acids and produce 3\' - phosphomonoesters', idx: 22 }
      //         ]
      //       },
      //       {
      //         label: '3.2 Glycosylases',
      //         idx: 1,
      //         children: [
      //           { label: '3.2.1 Glycosidases, i.e. enzymes that hydrolyse O- and S-glycosyl compounds', idx: 0 },
      //           { label: '3.2.2 Hydrolysing N-glycosyl compounds', idx: 1 },
      //           { label: '3.2.3 Hydrolysing S-glycosyl compounds (deleted sub-subclass)', idx: 2 }
      //         ]
      //       },
      //       {
      //         label: '3.3 Acting on ether bonds',
      //         idx: 2,
      //         children: [
      //           { label: '3.3.1 Thioether and trialkylsulfonium hydrolases', idx: 0 },
      //           { label: '3.3.2 Ether hydrolases', idx: 1 }
      //         ]
      //       },
      //       {
      //         label: '3.4 Acting on peptide bonds (peptidases)',
      //         idx: 3,
      //         children: [
      //           { label: '3.4.1 α-Amino-acyl-peptide hydrolases (deleted sub-subclass)', idx: 0 },
      //           { label: '3.4.2 Peptidyl-amino-acid hydrolases (deleted sub-subclass)', idx: 1 },
      //           { label: '3.4.3 Dipeptide hydrolases (deleted sub-subclass)', idx: 2 },
      //           { label: '3.4.4 Peptidyl peptide hydrolases (deleted sub-subclass)', idx: 3 },
      //           { label: '3.4.11 Aminopeptidases', idx: 4 },
      //           { label: '3.4.12 Peptidylamino-acid hydrolases or acylamino-acid hydrolases (deleted sub-subclass)', idx: 5 },
      //           { label: '3.4.13 Dipeptidases', idx: 6 },
      //           { label: '3.4.14 Dipeptidyl-peptidases and tripeptidyl-peptidases', idx: 7 },
      //           { label: '3.4.15 Peptidyl-dipeptidases', idx: 8 },
      //           { label: '3.4.16 Serine-type carboxypeptidases', idx: 9 },
      //           { label: '3.4.17 Metallocarboxypeptidases', idx: 10 },
      //           { label: '3.4.18 Cysteine-type carboxypeptidases', idx: 11 },
      //           { label: '3.4.19 Omega peptidases', idx: 12 },
      //           { label: '3.4.21 Serine endopeptidases', idx: 13 },
      //           { label: '3.4.22 Cysteine endopeptidases', idx: 14 },
      //           { label: '3.4.23 Aspartic endopeptidases', idx: 15 },
      //           { label: '3.4.24 Metalloendopeptidases', idx: 16 },
      //           { label: '3.4.25 Threonine endopeptidases', idx: 17 },
      //           { label: '3.4.99 Endopeptidases of unknown catalytic mechanism (sub-subclass is currently empty)', idx: 18 }
      //         ]
      //       },
      //       {
      //         label: '3.5 Acting on carbon-nitrogen bonds, other than peptide bonds',
      //         idx: 4,
      //         children: [
      //           { label: '3.5.1 In linear amides', idx: 0 },
      //           { label: '3.5.2 In cyclic amides', idx: 1 },
      //           { label: '3.5.3 In linear amidines', idx: 2 },
      //           { label: '3.5.4 In cyclic amidines', idx: 3 },
      //           { label: '3.5.5 In nitriles', idx: 4 },
      //           { label: '3.5.99 In other compounds', idx: 5 }
      //         ]
      //       },
      //       {
      //         label: '3.6 Acting on acid anhydrides',
      //         idx: 5,
      //         children: [
      //           { label: '3.6.1 In phosphorus-containing anhydrides', idx: 0 },
      //           { label: '3.6.2 In sulfonyl-containing anhydrides', idx: 1 },
      //           { label: '3.6.3 Acting on acid anhydrides to catalyse transmembrane movement of substances', idx: 2 },
      //           { label: '3.6.4 Acting on acid anhydrides to facilitate cellular and subcellular movement', idx: 3 },
      //           { label: '3.6.5 Acting on GTP to facilitate cellular and subcellular movement', idx: 4 }
      //         ]
      //       },
      //       {
      //         label: '3.7 Acting on carbon-carbon bonds',
      //         idx: 6,
      //         children: [
      //           { label: '3.7.1 In ketonic substances', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '3.8 Acting on halide bonds',
      //         idx: 7,
      //         children: [
      //           { label: '3.8.1 In carbon-halide compounds', idx: 0 },
      //           { label: '3.8.2 In phosphorus-halide compounds (deleted sub-subclass)', idx: 1 }
      //         ]
      //       },
      //       {
      //         label: '3.9 Acting on phosphorus-nitrogen bonds',
      //         idx: 8,
      //         children: [
      //           { label: '3.9.1 Acting on phosphorus-nitrogen bonds (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '3.10 Acting on sulfur-nitrogen bonds',
      //         idx: 9,
      //         children: [
      //           { label: '3.10.1 Acting on sulfur-nitrogen bonds (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '3.11 Acting on carbon-phosphorus bonds',
      //         idx: 10,
      //         children: [
      //           { label: '3.11.1 Acting on carbon-phosphorus bonds (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '3.12 Acting on sulfur-sulfur bonds',
      //         idx: 11,
      //         children: [
      //           { label: '3.12.1 Acting on sulfur-sulfur bonds (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '3.13 Acting on carbon-sulfur bonds',
      //         idx: 12,
      //         children: [
      //           { label: '3.13.1 Acting on carbon-sulfur bonds (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       }
      //     ]
      //   },
      //   {
      //     label: '4. Lyases',
      //     idx: 3,
      //     children: [
      //       {
      //         label: '4.1 Carbon-carbon lyases',
      //         idx: 0,
      //         children: [
      //           { label: '4.1.1 Carboxy-lyases', idx: 0 },
      //           { label: '4.1.2 Aldehyde-lyases', idx: 1 },
      //           { label: '4.1.3 Oxo-acid-lyases', idx: 2 },
      //           { label: '4.1.99 Other carbon-carbon lyases', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '4.2 Carbon-oxygen lyases',
      //         idx: 1,
      //         children: [
      //           { label: '4.2.1 Hydro-lyases', idx: 0 },
      //           { label: '4.2.2 Acting on polysaccharides', idx: 1 },
      //           { label: '4.2.3 Acting on phosphates', idx: 2 },
      //           { label: '4.2.99 Other carbon-oxygen lyases', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '4.3 Carbon-nitrogen lyases',
      //         idx: 2,
      //         children: [
      //           { label: '4.3.1 Ammonia-lyases', idx: 0 },
      //           { label: '4.3.2 Amidine-lyases', idx: 1 },
      //           { label: '4.3.3 Amine-lyases', idx: 2 },
      //           { label: '4.3.99 Other carbon-nitrogen lyases', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '4.4 Carbon-sulfur lyases',
      //         idx: 3,
      //         children: [
      //           { label: '4.4.1 Carbon-sulfur lyases (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '4.5 Carbon-halide lyases',
      //         idx: 4,
      //         children: [
      //           { label: '4.5.1 Carbon-halide lyases (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '4.6 Phosphorus-oxygen lyases',
      //         idx: 5,
      //         children: [
      //           { label: '4.6.1 Phosphorus-oxygen lyases (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '4.7 carbon-phosphorus lyases',
      //         idx: 6,
      //         children: [
      //           { label: '4.7.1 carbon-phosphorus lyases (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '4.8 Nitrogen-oxygen lyases',
      //         idx: 7,
      //         children: [
      //           { label: '4.8.1 Hydro-lyases', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '4.98 ATP-independent chelatases',
      //         idx: 8,
      //         children: [
      //           { label: '4.98.1 Forming coordination complexes', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '4.99 Other lyases',
      //         idx: 9,
      //         children: [
      //           { label: '4.99.1 Sole sub-subclass for lyases that do not belong in the other subclasses', idx: 0 }
      //         ]
      //       }
      //     ]
      //   },
      //   {
      //     label: '5. Isomerases',
      //     idx: 4,
      //     children: [
      //       {
      //         label: '5.1 Racemases and epimerases',
      //         idx: 0,
      //         children: [
      //           { label: '5.1.1 Acting on amino acids and derivatives', idx: 0 },
      //           { label: '5.1.2 Acting on hydroxy acids and derivatives', idx: 1 },
      //           { label: '5.1.3 Acting on carbohydrates and derivatives', idx: 2 },
      //           { label: '5.1.99 Acting on other compounds', idx: 3 }
      //         ]
      //       },
      //       {
      //         label: '5.2 cis-trans-Isomerases',
      //         idx: 1,
      //         children: [
      //           { label: '5.2.1 cis-trans Isomerases (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '5.3 Intramolecular oxidoreductases',
      //         idx: 2,
      //         children: [
      //           { label: '5.3.1 Interconverting aldoses and ketoses, and related compounds', idx: 0 },
      //           { label: '5.3.2 Interconverting keto- and enol-groups', idx: 1 },
      //           { label: '5.3.3 Transposing C=C bonds', idx: 2 },
      //           { label: '5.3.4 Transposing S-S bonds', idx: 3 },
      //           { label: '5.3.99 Other intramolecular oxidoreductases', idx: 4 }
      //         ]
      //       },
      //       {
      //         label: '5.4 Intramolecular transferases',
      //         idx: 3,
      //         children: [
      //           { label: '5.4.1 Transferring acyl groups', idx: 0 },
      //           { label: '5.4.2 Phosphotransferases (phosphomutases)', idx: 1 },
      //           { label: '5.4.3 Transferring amino groups', idx: 2 },
      //           { label: '5.4.4 Transferring hydroxy groups', idx: 3 },
      //           { label: '5.4.99 Transferring other groups', idx: 4 }
      //         ]
      //       },
      //       {
      //         label: '5.5 Intramolecular lyases',
      //         idx: 4,
      //         children: [
      //           { label: '5.5.1 Intramolecular lyases (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '5.6 Isomerases altering macromolecular conformation',
      //         idx: 5,
      //         children: [
      //           { label: '5.6.1 Enzymes altering polypeptide conformation or assembly', idx: 0 },
      //           { label: '5.6.2 Enzymes altering nucleic acid conformation', idx: 1 }
      //         ]
      //       },
      //       {
      //         label: '5.99 Other isomerases',
      //         idx: 6,
      //         children: [
      //           { label: '5.99.1 Sole sub-subclass for isomerases that do not belong in the other subclasses', idx: 0 }
      //         ]
      //       }
      //     ]
      //   },
      //   {
      //     label: '6. Ligases',
      //     idx: 5,
      //     children: [
      //       {
      //         label: '6.1 Forming carbon-oxygen bonds',
      //         idx: 0,
      //         children: [
      //           { label: '6.1.1 Ligases forming aminoacyl-tRNA and related compounds', idx: 0 },
      //           { label: '6.1.2 acid-alcohol ligases (ester synthases)', idx: 1 },
      //           { label: '6.1.3 Cyclo-ligases', idx: 2 }
      //         ]
      //       },
      //       {
      //         label: '6.2 Forming carbon-sulfur bonds',
      //         idx: 1,
      //         children: [
      //           { label: '6.2.1 Acid-thiol ligases', idx: 0 },
      //           { label: '6.2.2 Amide---thiol ligases', idx: 1 }
      //         ]
      //       },
      //       {
      //         label: '6.3 Forming carbon-nitrogen bonds',
      //         idx: 2,
      //         children: [
      //           { label: '6.3.1 Acid—ammonia (or amine) ligases (amide synthases)', idx: 0 },
      //           { label: '6.3.2 Acid—amino-acid ligases (peptide synthases)', idx: 1 },
      //           { label: '6.3.3 Cyclo-ligases', idx: 2 },
      //           { label: '6.3.4 Other carbon-nitrogen ligases', idx: 3 },
      //           { label: '6.3.5 Carbon-nitrogen ligases with glutamine as amido-N-donor', idx: 4 }
      //         ]
      //       },
      //       {
      //         label: '6.4 Forming carbon-carbon bonds',
      //         idx: 3,
      //         children: [
      //           { label: '6.4.1 Ligases that form carbon-carbon bonds (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '6.5 Forming phosphoric-ester bonds',
      //         idx: 4,
      //         children: [
      //           { label: '6.5.1 Ligases that form phosphoric-ester bonds (only sub-subclass identified to date)', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '6.6 Forming nitrogen—metal bonds',
      //         idx: 5,
      //         children: [
      //           { label: '6.6.1 Forming coordination complexes', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '6.7 Forming nitrogen-nitrogen bonds',
      //         idx: 6,
      //         children: [
      //           { label: '6.7.1 Forming diazo bonds', idx: 0 }
      //         ]
      //       }
      //     ]
      //   },
      //   {
      //     label: '7. Translocases',
      //     idx: 6,
      //     children: [
      //       {
      //         label: '7.1 Catalysing the translocation of hydrons',
      //         idx: 0,
      //         children: [
      //           { label: '7.1.1 Linked to oxidoreductase reactions', idx: 0 },
      //           { label: '7.1.2 Linked to the hydrolysis of a nucleoside triphosphate', idx: 1 },
      //           { label: ' 7.1.3 Linked to the hydrolysis of diphosphate', idx: 2 }
      //         ]
      //       },
      //       {
      //         label: '7.2 Catalysing the translocation of inorganic cations',
      //         idx: 1,
      //         children: [
      //           { label: '7.2.1 Linked to oxidoreductase reactions', idx: 0 },
      //           { label: '7.2.2 Linked to the hydrolysis of a nucleoside triphosphate', idx: 1 },
      //           { label: '7.2.4 Linked to decarboxylation', idx: 2 }
      //         ]
      //       },
      //       {
      //         label: '7.3 Catalysing the translocation of inorganic anions and their chelates',
      //         idx: 2,
      //         children: [
      //           { label: '7.3.2 Linked to the hydrolysis of a nucleoside triphosphate', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '7.4 Catalysing the translocation of amino acids and peptides',
      //         idx: 3,
      //         children: [
      //           { label: '7.4.2 Linked to the hydrolysis of a nucleoside triphosphate', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '7.5 Catalysing the translocation of carbohydrates and their derivatives',
      //         idx: 4,
      //         children: [
      //           { label: '7.5.2 Linked to the hydrolysis of a nucleoside triphosphate', idx: 0 }
      //         ]
      //       },
      //       {
      //         label: '7.6 Catalysing the translocation of other compounds',
      //         idx: 5,
      //         children: [
      //           { label: '7.6.2 Linked to the hydrolysis of a nucleoside triphosphate', idx: 0 }
      //         ]
      //       }
      //     ]
      //   }
      // ]
    }
  },
  methods: {

    fnGetList (enzymeNum) {
      if (enzymeNum === 'Empty') {
        return
      }
      console.log(enzymeNum)

      // EnzymeNumber 구하는 Logic
      this.chosen_enzyme = ''
      this.cmpenzNum = 'r'
      this.precmpenzNum = ''
      this.viewnum = ''
      this.enzymeslist = []
      this.enzymeNamelist = []

      if (enzymeNum !== null) {
        this.enzNum = ''
        this.chosen_enzyme = enzymeNum
        console.log(enzymeNum)
        for (let i = 0; enzymeNum[i] !== ' '; i++) {
          this.enzNum = this.enzNum + enzymeNum[i]
        }
        console.log('enzNum: ', this.enzNum)

        let count = 0
        for (let i = 0; this.enzNum[i]; i++) {
          if (this.enzNum[i] === '.') {
            count = count + 1
            if (count === 3) {
              break
            }
          } else {
            this.viewnum = this.viewnum + this.enzNum[i]
          }
        }

        for (let i = 0; i < this.enzNum.length; i++) {
          if (this.enzNum[i] !== '.') {
            this.cmpenzNum = this.cmpenzNum + this.enzNum[i]
            this.precmpenzNum = this.precmpenzNum + this.enzNum[i]
          }
        }

        // 두번 눌렀을때 데이터 중복되는거 해결해야함

        console.log('cmpenzNum:', this.cmpenzNum)

        axios.post('http://localhost:3000/api/board', this.sendData = 'SELECT * FROM Myenzyme_' + this.viewnum + " WHERE EC='" + this.enzNum + "'"
          /* this.sendData = "SELECT distinct description from enzymes WHERE EC LIKE '" + enzNum + ".%'" */).then((res) => {
          if (res.data.success) {
            alert('sending data successed...')
          } else {
            alert('sending data failed...')
          }
        })
          .catch((err) => {
            console.log(err)
          })

        axios.get('http://localhost:3000/api/board')
          .then((res) => {
            for (let i = 0; res.data.data[i] != null; i++) {
              // console.log(res.data.data[i])
              this.enzymeslist[i] = res.data.data[i]
            }

            const json = JSON.stringify(this.enzymeslist)
            this.remove_obj = JSON.parse(json)
            this.obj = JSON.parse(json)

            // 중복된 json데이터 삭제
            this.enzymeNamelist = [...new Set(this.remove_obj.map(x => x.Description))]

            // for (let i = 0; i < 7; i++) {
            //   for (let j = 0; this.simple[i].children[j] != null; j++) {
            //     for (let k = 0; this.simple[i].children[j].children[k] != null; k++) {
            //       if ((this.simple[i].children[j].children[k].idx).toString() === this.cmpenzNum) {
            //         // Select enzyme를 없애기위해 추가
            //         this.simple[i].children[j].children[k].children.splice(0, 1)

            //         // json에 데이터를 직접 추가하는 부분
            //         for (let l = 0; this.enzymeNamelist[l] != null; l++) {
            //           const data = {}
            //           data.label = this.enzNum + ' ' + this.enzymeNamelist[l]
            //           data.idx = l
            //           console.log(data)
            //           // this.simple[i].children[j].children[k].children.push(data)

            //         }
            //       }
            //     }
            //   }
            // }

            for (let i = 0; i < 7; i++) {
              for (let j = 0; this.simple[i].children[j] != null; j++) {
                for (let k = 0; this.simple[i].children[j].children[k] != null; k++) {
                  // if (i === 0 && j === 0 && k === 1) {
                  for (let h = 0; this.simple[i].children[j].children[k].children[h] != null; h++) {
                    // json에 데이터를 직접 추가하는 부분
                    if (this.simple[i].children[j].children[k].children[h].idx === this.cmpenzNum) {
                      this.simple[i].children[j].children[k].children[h].children.splice(0, 1)
                      for (let l = 0; this.enzymeNamelist[l] != null; l++) {
                        const data = {}
                        data.label = this.enzNum + ' ' + this.enzymeNamelist[l]
                        data.idx = l
                        console.log('data: ', data)
                        this.simple[i].children[j].children[k].children[h].children.push(data)
                        // console.log(this.simple[i].children[j].children[k].children[h])
                      }
                    }
                    // }
                  }
                }
              }
            }
          })
          .catch((err) => {
            console.log(err)
          })
      }
    }

  }
}
</script>

<style lang="sass" scoped>
.row > div
  padding: 10px 15px
  border: 1px solid black
.row + .row
  margin-top: 1rem

</style>

<style>
.enzymeTitle {
  font-weight: bold;
  font-size: 1.3rem;
}
</style>
