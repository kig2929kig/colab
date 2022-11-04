{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": [],
      "authorship_tag": "ABX9TyMMpHBAPM214OMlSHlmVBsp",
      "include_colab_link": true
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "markdown",
      "metadata": {
        "id": "view-in-github",
        "colab_type": "text"
      },
      "source": [
        "<a href=\"https://colab.research.google.com/github/kig2929kig/colab/blob/main/pandas1.md\" target=\"_parent\"><img src=\"https://colab.research.google.com/assets/colab-badge.svg\" alt=\"Open In Colab\"/></a>"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "\n",
        "\n"
      ],
      "metadata": {
        "id": "8Pqw1m_Kg8C4"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "# pandas\n",
        "+ Python 프로그래밍 언어를 기반으로 구축된 데이터 분석 및 조작 도구(오픈 소스).\n",
        "+ 홈페이지 : https://pandas.pydata.org/  \n",
        "\n",
        "## 1. 설치\n",
        "+ `pip install pandas`\n",
        "+ 코랩(colab)에서는 기본적으로 pandas 라이브러리를 지원.\n",
        "\n"
      ],
      "metadata": {
        "id": "pVRsD7r3CFnQ"
      }
    },
    {
      "cell_type": "code",
      "execution_count": 20,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 143
        },
        "id": "fDfNcEeMA6Ao",
        "outputId": "f1a31db1-72f3-4a45-82b9-f5be03dc0a6c"
      },
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "    이름  나이 성별\n",
              "0  홍길동  22  남\n",
              "1  이순신  35  남\n",
              "2  콩순이  58  여"
            ],
            "text/html": [
              "\n",
              "  <div id=\"df-a0daa001-82eb-44f5-8d94-ab3b411cd104\">\n",
              "    <div class=\"colab-df-container\">\n",
              "      <div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>이름</th>\n",
              "      <th>나이</th>\n",
              "      <th>성별</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>0</th>\n",
              "      <td>홍길동</td>\n",
              "      <td>22</td>\n",
              "      <td>남</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>1</th>\n",
              "      <td>이순신</td>\n",
              "      <td>35</td>\n",
              "      <td>남</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>2</th>\n",
              "      <td>콩순이</td>\n",
              "      <td>58</td>\n",
              "      <td>여</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>\n",
              "      <button class=\"colab-df-convert\" onclick=\"convertToInteractive('df-a0daa001-82eb-44f5-8d94-ab3b411cd104')\"\n",
              "              title=\"Convert this dataframe to an interactive table.\"\n",
              "              style=\"display:none;\">\n",
              "        \n",
              "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\"viewBox=\"0 0 24 24\"\n",
              "       width=\"24px\">\n",
              "    <path d=\"M0 0h24v24H0V0z\" fill=\"none\"/>\n",
              "    <path d=\"M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z\"/><path d=\"M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z\"/>\n",
              "  </svg>\n",
              "      </button>\n",
              "      \n",
              "  <style>\n",
              "    .colab-df-container {\n",
              "      display:flex;\n",
              "      flex-wrap:wrap;\n",
              "      gap: 12px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert {\n",
              "      background-color: #E8F0FE;\n",
              "      border: none;\n",
              "      border-radius: 50%;\n",
              "      cursor: pointer;\n",
              "      display: none;\n",
              "      fill: #1967D2;\n",
              "      height: 32px;\n",
              "      padding: 0 0 0 0;\n",
              "      width: 32px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert:hover {\n",
              "      background-color: #E2EBFA;\n",
              "      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "      fill: #174EA6;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert {\n",
              "      background-color: #3B4455;\n",
              "      fill: #D2E3FC;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert:hover {\n",
              "      background-color: #434B5C;\n",
              "      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
              "      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
              "      fill: #FFFFFF;\n",
              "    }\n",
              "  </style>\n",
              "\n",
              "      <script>\n",
              "        const buttonEl =\n",
              "          document.querySelector('#df-a0daa001-82eb-44f5-8d94-ab3b411cd104 button.colab-df-convert');\n",
              "        buttonEl.style.display =\n",
              "          google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "\n",
              "        async function convertToInteractive(key) {\n",
              "          const element = document.querySelector('#df-a0daa001-82eb-44f5-8d94-ab3b411cd104');\n",
              "          const dataTable =\n",
              "            await google.colab.kernel.invokeFunction('convertToInteractive',\n",
              "                                                     [key], {});\n",
              "          if (!dataTable) return;\n",
              "\n",
              "          const docLinkHtml = 'Like what you see? Visit the ' +\n",
              "            '<a target=\"_blank\" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'\n",
              "            + ' to learn more about interactive tables.';\n",
              "          element.innerHTML = '';\n",
              "          dataTable['output_type'] = 'display_data';\n",
              "          await google.colab.output.renderOutput(dataTable, element);\n",
              "          const docLink = document.createElement('div');\n",
              "          docLink.innerHTML = docLinkHtml;\n",
              "          element.appendChild(docLink);\n",
              "        }\n",
              "      </script>\n",
              "    </div>\n",
              "  </div>\n",
              "  "
            ]
          },
          "metadata": {},
          "execution_count": 20
        }
      ],
      "source": [
        "import pandas as pd\n",
        "\n",
        "passenger = {\"이름\" : [\"홍길동\", \"이순신\", \"콩순이\"],\n",
        "             \"나이\" : [22, 35, 58], \n",
        "             \"성별\" : [\"남\", \"남\", \"여\"],\n",
        "             }\n",
        "#print(passenger['name'][0])\n",
        "df = pd.DataFrame(data = passenger)\n",
        "df"
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "## 2. pandas 데이터 구조\n",
        "\n",
        "![그림1.png](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAqoAAAIPCAYAAAHMU8yhAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAAAJcEhZcwAAFxEAABcRAcom8z8AAJzZSURBVHhe7Z0F1PPG8fX/X9MwMzNzGmZ+04aZqUkaTpqkYeakYWjaJA0zU8PMzMzMzNx0v/fOM2uv9xnJki2j7u+ceyztjmR5PTsar+TV/xFCmmWNg+ZxRUh3110MPSoH6WoqeWyzUESjdG3DhviGi6XVUq+LNbZ+3XpNo3QNq6uDGifPOpbj+pi+btiwAZKWPXnW4zqL0nhsu+nbhh16ROKVnRIaxSrPo3Af+rE6h+sSpFGaxHssGzaADdsi2LABI4wwghsyZIgsTzrppG6RRRZxI400kttll13csMMOK+We//73v26sscZyI488srvyyivdcMMN57baaiutHdywP//8sy5V+eKLL9xvv/2ma4Ppm4ZF4y255JJuueWWc4suuqhbcMEF3fDDD+/GGWccd/XVV6vVAJNMMon76KOP3Pvvv+/mnXded8EFF7jxxx9fa6sNO/vss8tr3LBvvfWWvN54443yatE3DVskscc2AhvWoC8adomdTq+8sR5TDR9//HHbhUaxyrPIU69hw8/dEuo17I8//th2oVGs8izysGENdbRhd7zLLs9L1obdbLPN3K+//lrzIaDvv/9e5NfBt99+W2OTpP/9739ut912k21uuummSnnWhl1ooYXkdd99962UeZpqWK9myNqwt912mxtjjDEq615oHAjL/oOiYd988003zTTTiMYbb7yabUKdfvrp8rr++utXyrI2rH/v/fffv1LmKcxjw3W/HL9aZG1YVL/33nuVdS+PX59rrrnc3HPPLcs//PCDyNfFQq77yy+/uMMOO6ymN2RtWPzQwOtee+1VKfO0tGFBvcbN2rDtVNaGteRpuGGLgg3bIuo1bCdAozRLxxs2RI+p47SjYduKHlPHyduwxxxzjC5V6ZmGxVBgXpCepYFU6eyzz5Y8NCRrwy688MLyuvfee8trSN957LTTTqtL2dh4443lde2115ZXkMdj8X6HH364rlXpu4Z98cUXRQB5r1+2wI8IcNZZZ8mrJ0/DvvDCC26//fbTtSp917BFkKdhk2DDGpSiYa0kvNVCo1jlWeRhwxoqVcOGy6FwAoL8+tRTT11Z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btVVV63Zb1YBPGAc+PVRRhkl0emLdla00THHHFP5fBgvjm1i2u6sIXAkr5BwPWkZ+PU0m3oU6azQK6+84h577DF52EVcF+vpp592c845p1t44YXl9amnnqqpH2200aTOy78fHMpvN88888gc4eF2WfTwww+7hx56yD3wwAOyjmXo/vvvH2QLtcJZ/WeA9t1330E2MR1xVjhUkuPFWHb1tk9atijaWftVRTtrFsV0xFm7CTprNtFZuwDvrFS64CRWeTvlndWqyyP96vsH7cwDpETWsgAn6TTeWfUrEuS7yRFZ+xJtnwFyOitGBLLg71bCHU/40WQ9dzjpjqT77rtPlxrnnHPOcU8++aQsP//88+7cc891b731lqzHFO2s/gej56CDDtKlZOisCWj7DJDTWa0HYVv4J457sj4k2983Ouqoo8prM+y2227yil/je++9tyxbFO2suP8V98RCuJd111131Zpk6KwJaPsM0CJnBVdddZUu2c467rjj6lJruOSSS3RpgNVXX12XainaWQGG+TzoLPWgsyag7TNATmftR1rhrHmhsyag7TMAnZXO2s1o+wyQ4qzW+GA/Ck5ilbdSMXTWBLR9BqCz0lm7GW2fAVrorPjjXSirPi7z5f7+A7z6u6hapaKdFceMz+Dva3j11VcH2cTQWRPQ9hkgo7O+++67cvcQ/mb897//vabO0i677OK23HJLN9ZYY8nrrLPOWqkDhx9+uLzidkOALxb/RMUNJ94GwFGB3zaL7r77btkGYH3PPfeU5UkmmWSQLVSks3qw/Mgjj8jyUUcdlWjnobMmoO0zQEZnhXC7GzbHbXxxXSjvYBa4jxVfHoR7XP3ywQcfLBEJHQL7P/bYY+ViQiPO6reBk2L9pptukvdAB7KOvUhnxTFjHgQsY/gK74u5BWK7GDprAto+A0SrIWHjvv/++xIl8X957CKssxRfhUK083UWSR2gEWe966675F7Y5557TtZff/11t8oqq4jjxLZQkc5qCR0xLouhsyag7TNAtBoSN3C/qtXOaimGzpqAts8AdFY6azej7TNAirOWBThJp6GzJqDtMwCdlc7aK7Axunfma3w3/H4CfIOUWXASq7yd8s5q1elXRQifKUB6CDor6RnorKRnoLOSnoHOSnoGOivpGeispGfwjtIN0kMihBBCCCGEEEIIIYSQfiEc98SyV0ze8dG89lloxT5JDxE6AJa9Qqz1sMyvx2XhKwiXQbhNuAz8elgG4nVSMkLH8LKwyuMyvx6/Amv7JJK2y7MP0ofUc4DYWbw8SWX+1aqvR2ibtEyICZ2EEEIIIYQQQgghhBBSGqz/PXVKekiEDMZymE5JD4mkMbSVWjZDXav2WwTd4iR01AZJc6q0ul6DjtrjeGfEq5dUDCVpPSxLI7ZPW4+FemCVNQIdtcexHMCXWXUgrdzLr0tFhFVvLYdlzUJH7XG8M+A1XA5fAZat8jRCOyz79fgVWMt4DSWVDUJH7WHCL99atspAuJxG0jZ+2SoD4XJR0FF7DDiBlxYJYVlYFy97aVEqsZ3f1pf7V5C27KVFDUFHJT0BHZX0BHRU0hPQUXuAoS1TyfPKKu+oVl07lXQM+lWVE316otkwZRMdtYtRNx1ojJJTcdQOg2PQr6cCHdVDR6WjdjPaNnTUodBRuxhtGzrqUOioXYy2TV856thjj61L+SjCUR977DH3/vvv61pj0FENtG3a6qiXXnqpG2aYYdwhhxzizjjjDCkbbbTRKg423XTTSf2www7rXn75ZSlbZ5113Pjjjy/Ladx9991uqqmm0jXn5plnHrfLLru43/3ud7I+1lhjuVVWWUWWY2JHHW644dxCCy3kppxySlkfY4wxRABlqNtnn33ca6+9JmXrr7++HDcc9aOPPnJ77bWXW2KJJaRu4403luPfd999ZT0NOqqBtk1bHfWqq65yP/30kyzPNNNM8urX8YXONddcYgPOPfdcN+6448ry448/7t566y1ZTgLODfbYYw959R1hxBFHdM8//7x78cUXZX2CCSaQ15DQUS+55BL33//+V5Znn312t/nmm8sy+Mtf/iJlADaw9Z3MR9Thhx/e/fzzz+7vf/+7lG+99dbymgU6qoG2TUcd9aKLLnIPPPCArKc5ahYQwc4//3w3xxxzyPrFF18sryOMMII4atppOXRUvK8ndlRQz1ERjT3/+9//6KjNom3TVke98sorK446wwwzyOsss8zi5p13Xjktw8lgA8455xxxhgsuuECiVD3WXXddecUpGBx//PFuzjnndKOOOqqsYx///ve/ZTkmdNRvvvnGLb300nJ6x7GBP/zhDyLgy3Bs6Aw//viju+yyyySiv/fee+6ee+5xr776qht99NHFbsstt5TXLNBRDbRt+urHVAjyxoUXXtj99ttvWpJM6KgAeXOWvLho6KgG2jZ966h5iB21U9BRDbRt6KhDoaN2Mdo2dNSh0FG7gCV2Ot1R6fKOatW1U0Udg371vUXSgWsnTo2oH374ofv444/7Xt5RrbpWKgbHoF9PBXw/uliX0joqhl7KIO+oVl0rFUNHNdC2oaMOFR21C6Cj1hcdtQugo9ZXqR11x7uq9n45LGsXnXLUH374QfdSBVeJUIfLj+edd57opptukrLFF19cXn/99ddKndd1111X2W8rVLSj4jIxPodff/LJJ+UzhzZQTFsdFc5oydcVTb19FumoANfocc08rouFL+urr75y33//vQjLuI4e280666zyuuKKK8orwLahTSM6+OCDK7f9YX3IkCFukkkmMfddtKPCSf37Qs8880zNuldMWx0VWA4aroNwuZUU6ahrrbWWlONLDyOGJTDFFFPIK5hxxhnl1dfDYaaZZhq5wwjr3lERdQ844AB3+OGHu0MPPVSWTznllMp2WYX94na7a665RtaxDD777LNBtq1yVM/TTz8trzjLhHYxbXVUywF9WZqjhjZenqRlj1XmKdJRcQcSXuFAVn0sOKMnjGQATgp82RprrCGvuLUPdVNPPbUIyxBupPa2WYX3vP766yvrOP22w1EhdBSv5557zuzYMW11VOAdzTtQ/BqTVG9tb9mGyzGdclTc14n7TeEoEG6Ju/DCCyUNgMN8++23su61/PLLV7YFuG0Peumll2r2m1WXX365u/baayvruOseuWJo49UKR91zzz0rn+3oo4/uvhw1xDtWmiOFxHZ+PX4FScsxRToqbmp+9tlnsb9BdbHACiusIK9g9dVXl1df//nnn8vfRXCzNIS/jfjtQLgf4NezyEfyX375RZYffPDByrpl3ypH9cvIUbsyogLLebI6lyfJBuVZ91Wko6Kx8beQDz74YFBdLDjFrbfeKveEQjfccEONo8BRF1100Ur9jjvuWKl76KGHKuVnnnlmpTyPsA/ok08+cV9++WVlHRE9tm2Fo+I/Vf4z4Aburo2osfPUW/eg3CskXE/a1qJIR+1XtcJRsyimI45ajzzOlka9/dBR64uO2gXQUeuLjtoF0FHri47aBTTjqGXBO2qnKb2jUunyjmrVtVNFHYN+9f2BdmJG1KF4R+00OAb9eirg+9HFcqJtQ0cdCh21i9G2aauj4upT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TCp9RxZJKVGfqcU7Bik1YSApO2FbaNcxqfQdWSSlRH2mFu8YpGu44IIL3CabbKJr7SEMJJ3k9ddfd+uss477/PPPtaT9hG2hXcek0ndkkZQS9ZlavGP0Gd9884179dVX3WuvveZeeukl0csvv6y1VVBm1b355puy7SuvvOL++9//yvL777+vtQN89913lW3fe+89LW0OvNfWW2/txhtvPPfJJ59oaZUvvvhC3g/yx/e///1Pa5179913K5/3hx9+0NL6hIHEAsEO+/Rt+sYbb2jNAEntCDvYYztf/+GHH2rtAN9++22l7pprrnHDDz98TVt/9NFHlf1//fXXWjoA6rB/yO8DbdIMYVto1zGp9B1ZJKVEfaYW7xh9xlVXXeVGHnlk9+STT2qJc8sss4ybbrrpZPnAAw90I4wwgvv4449l/dNPP3UTTTSRO+CAA2R9rrnmcvPPP7/75z//Kft54YUX3CijjOLOPvtsqV9kkUXcRhtt5H777TdZv+yyy9xkk03mPvjgA1lvlGeeeUbeZ8wxx3QLLriglg4w++yzu/3220/XnDv++OPdSCON5H7++WcJXpNMMom7/vrrpQ7BeY011nBLLrmkrNcjDCQht956qxt33HHluAAC9QILLCDHAg499FA34YQTVk4AeMU6ygHsYB8GeLT7RRddJMv4jJtttlnlxHDxxRdLPYIqTozTTDONO+2006QO7LDDDm6eearHiBPQxBNPLMG1KMK20K5jUuk7skhKifpMLd4x+gwEVXTOn376SUucGzJkiJtpppl0zbmHHnpIbNZaay235ppruimmmMJtvPHGUoegisDpgzNAADv33HNlGZnk3HPP7VZffXW32mqryfbrrrtuJUjnxQeVEUcc0e2+++7uzjvvdKOPPnolyAMcxxlnnKFrzl155ZVij6D6/PPPuzHGGMMtt9xycjyrrrqq23DDDUVZCANJyCWXXCLvgSDtWWyxxSpBdfPNN3eTTz65fH7/vptuuqk78cQTpR52sPdgP9gf9gvGHntst88++8gyeOyxx9xwww0nQRVZOdpg6aWXrux7vfXWk+EBD4IqgniRhG2hXcek0ndkkZQS9ZlavGP0GfWC6l/+8hc3/vjjy7IPaJNOOmnmoIpscu+995ZlgJ/HCGpvvfWWluQH77/++uvrmpMAPeyww7oHH3xQ1u+44w45FgQb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+k0VdQoRKTVhMCkzYTtot0nE9x1dJWVE/aaKOoWIlJowmJSZsB202yTi+46ukjKiflNFnUJESk0YTMpM2A7abRLxfUdXSRlRv6miTiEipSYMJmUmbAftNon4vqOrpIyo31RRpxCRUhMGk07xv//9T5dql9tJ2A7abRLxfUdXSRlRv6miTiEiXcOGG27obrjhBl1rD2Ew6SR/+9vf3AEHHKBr7SdsB+02ifi+o6ukjKjfVFGnEJGuYdRRR3UnnHCCrrWHMJh0kllmmcUtscQSutZ+wnbQbpOI7zu6SsqI+k0VdQpRn/Haa6+JXnnlFffyyy+LPvvsM60d4PPPP6/Uffrpp1rq3E8//STbYfs33njD/fzzz+6ll17S2iqvvvqqlFt1jfLOO++4Mccc0+23337ut99+09IqOFa8H94bx/fBBx9ozQD+eFCXhzCYxKA9wv2ibX788UetddKuVhvDxrej3x6K8e348ccfu5lnnnlQUPXbYV8xfv/+/V988UX33XffaW1+wnbQbpOI7zu6SsqI+k0VdQpRnzHGGGO4kUce2a200koSoHbaaSe30EILSccFP/zwg5t77rnd9ttv73beeWfJkL766iupe+aZZ9ywww7rhhtuODfRRBO5v/71r+g47qijjpJ6cP3114vNkUce6aaffnp3yCGHSHmzY4ETTzyxm2qqqeTYfQDy+zznnHMkiz366KPdpJNO6sYee2y3+uqrSx3Yd9993WyzzeaOOOIIObZbb71Va+oTBhOPf18MRyy//PLu4IMPlnZAuzz66KNS9+2337o55phD2hfCMsoAbGCLbQ466CDRjDPO6I499lipB9dcc43YoG3xHUw++eQ1QfX44493k0wyiXzmEUYYwV166aVaM8Dvfvc7N8www7gdd9xRPv/uu++e+4QSErYD+kwa0m/khZQW9Zsq6hSiPmOyySZzK6+8svv1119lHZkoOt+DDz4o6whKe+65pywDdOqZZppJ7J9//nnpwPfff78E1T//+c9us802c+OOO67YXnbZZbKMDAsgM0JghU2j+ACGY/AnBH8CADi+8ccf33344Yeyjs+Dz7jRRhvJ+gYbbCABFScL8MILL8gxXnfddbJejzCYhAwZMkROTL4dEajRNk888YQcMwLhYYcdJnUAyyhDHWxgGwb3zTffXD4HuPDCC+UYX3/9dVn/5ptv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hJCy4LIQBQqKosotKyGBLFuqHLL8AbJsm5GeugghZUFT0XSiQCEihJQWKyGBSHmx/AHSU01DDDrvSBEhpFRojEknChQiQkhpsRISiJQXyx8gPdU0xKDzjhQRQkqFxph0okAhIoSUFishgUh5sfwB0lNNQww670gRIaRUaIxJJwoUIkJIabESEoiUF8sfID3VNMSg844UEUJKhcaYdKJAISKElBYrIYFIebH8AdJTTUMMOu9IESGkVGiMSScKFCJCSGmxEhKIlBfLHyA91TTEoPOOFBFCSoXGmHSiQCEihJQWKyGBSHmx/AHSU01DDDrvSBEhpFRojEknChQiQkhpsRISiJQXyx8gPdU0xKDzjhQRQkqFxph0okAhIoSUFishgUh5sfwB0lNNQww670gRIaRUaIxJJwoUIkLIIHbYYYeh3eP/3DDDDOOOPPJILe0/rIQEKisPPfSQm2yyyeS7n2uuudy7776rNeXB8gdITjQNUjnfBNIqQkhZ0BiTThQoRKRr+d///qdLzZNlX6FNo+9tbZf3vTtFeAwHHHCAG2WUUdzYY4/tTjvtNC1NP868nyG0z7Jt3v1nwUpIoHo081kbodHtre3S9vXSSy+52WabzQ077LBuiSWWcO+//77WDJDlOPK+ZxqNbtcMlj9AeqppiEHnHSkihJQKjTHpRIFCRLqam266yc0333xuzjnndAsuuKAIy7PMMoubddZZ5RWaaaaZ3AknnKBbVU9w4YnuX//6l9j5bbD9DDPM4I444gi1qLV/+eWX3bLLLisnbv/eWB4yZIj7+OOP3QsvvOAWWGABN+WUU7rttttOt7Lf+7bbbnPzzDOPm3HGGSvvPd1007nNN9/c/fbbb2IT2neKxx57TBIUfKbJJ5/cTTHFFLK88soruzfffFOtagmP++STT3YzzzxzpY3RXvj+0HZoK9TtuOOO7pdfftEtqtt///33bv3115d28d8t2gvbYaTPU2Q7WQkJlET43k888YRbZJFFxIf8dzr33HPX+MoyyyzjnnvuOd2idvvjjjtOPp//rHjFOso9oT32g/2F/oj3w3ah0H4777yzblXdR7ivG264QUZMfX/Advie4KNTTTWVG2OMMQYlquH2u+++u5t++ullO2yP73X22Wd3l1xyiVrU2nv22msvscV3iuOff/75ZTt/DNDUU08tx/bAAw/oVu3F8gdITzUNMei8I0WEkFKhMSadKFCISFdz1VVXyaXI8ccfXxInnKRvvPFGrR3g66+/dn/84x+Hfp3/J4nV/fffrzUDwB7bYoRwzTXXFHuAZGnjjTd2o48+uptoooncFVdcIeWe559/Xk6YY401lpw8kSDjRIr3GG+88eQViQKSC6xjP2eccYZuPQCS3YUXXtiNMMIIcmJ+6qmntMa5Qw45RN53tNFGc4cddpj79ddftaZzIDnA5xl33HGlzSB8fiQUr732mloN5tZbb5WEFm28xhpruK+++krK0cZ//vOf3aSTTir1SIA22mgj9/PPP0s9+OmnnySBwbb4ro8//nitcfJdoo2HH354SdLefvttrSkGKyGB0kDytsIKK8gxzTHHHO6OO+7QmoEfQ9NMM418VoxGIwlDQhty7bXXSnvge19vvfXcDz/8IOV4xTrKUX/ddddJuQf7wf6wX+wf74P3i9lyyy1lRHTMMcd0559/vpYOgGR33nnnFX9Eko0fW55999238sME21ojqv/+97/l/ccZZxy30047aamT7wXfz0gjjSR95JFHHtGaWrbeemvxAbwPPuNaa63lvvnmG60djJXsthrLH6CBM01j1JxzVFpFCCkLGmPSiQKFiHQ1PlFFUrDJJptoae0J7MMPP5RRzuGGG05GiMLRt1NPPVVG6XDPJRJPizvvvNNNMskkQ93h/9xqq61WSaJ8ovr73//eLbbYYpJ03XzzzW6CCSZwI444ottzzz3Fbo899pD1CSec0J177rlSBo4++mhJGJAUHHzwwVpaC0ZmkYjhvXGCf/3117WmvaA9kQghWUFSvtJKK7n99tvP7b333m7JJZeUdsXnCRMbD74XHD+S9YsvvlhLXWWkGKDdkJigLcJE9ZlnnpGEC9svuuii7rvvvpPymF133VXaEu18yimnaGnzWAkJlAS+XyTUuHcXSZcHn9X7JH4Ioc3gN2GiCpt11llHPit8BVcLLFCOetjB3rejT1SxX+zf/+AK+8J///tft9lmm0k7wafDEU78MMK2I488sjv00EO1tPZ7wg8r/BiML/1//vnn8v3gmDBim9SX0N/wgw12u+22m5ZWQZshmcXnu/zyy7W0MwlpEpY/QEM/U8MM3XjQuUerCCFlQWNMOlGgEJGuxieqSHA22GADGX2LSUtUQ7AvXMLGaNjyyy/vVlxxRVnH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ynqz9MOI6i+//CKf5aWXXpKR8ptuusndfPPNoltuucW9+OKLUp/UJwDa4L777nPXXXddZVsI/v7JJ5+ITTOj75ashASybKla+UR10003dQsttJB7//335TuybC0BJKqzzDKL23fffWUdYL9QozGNiWpxtPq83TLCpCeLLNLq0+rSaHS7shC2TyfaqNUOrzEmnShQiFpIM4mqv7z86KOPyuXo2WabzY088shu+OGHd8MOO6wbYYQRZEQOCdNRRx3lPvjgA7G39tVOYRQUnzvk2GOPdVtuuaV8jiRttdVW7u9///ugk0xSglpPPvEDOIHiRHjggQe6q6++2n3++ec1+wV5E1WM4DJRHRB44YUX3F//+lcZGTv11FPdySef7M466yzxzUkmmcRNPvnkbu+99xY74LdFgouk5JJLLnGbb765O+aYY9y///1v2f6cc85xm222mfg82vuMM85wX3/9tdiH79+MrIQEsmypWhWRqD733HNunnnmEW277bZu6623lhFaLD/11FNiY22bJiaqxdHq83ZLyJrs1LOL65OUlUa2KSOdbKdWO7zGmHSiQCFqIY0mquEo4ZVXXukmnnhi97vf/U5GHd98803ZL0appp122qEf4f/kJPHOO++IvbW/dgogGcGIKJKTZZZZxt17772SHGL0N0lI/h5++GG5FI7tkJg8+eSTsj/rfdKE9vMgQZ1wwgndqKOO6k466SQpQ3IU2oO8iSpGfkcZZRQZoYVmmmmmijBChBPvH/7wh5ryWEjg1lhjDffRRx/Jfq336wXBV5FA4nvE94z2RRlekYTjx8vxxx8vtzv85z//GfRZYYMRU/gwbMPtoXfffVdG3Zdeemlp+3j7ZmQlJJBlS9WqiEQVI6r4Eb7DDjuID2AfuJUHvgSfamRUlYlqcbT6vF04jSQ5SdsklYO0Oos89pZtWBbXhVh2SUoii01M3m3q2derbxWtdniNMelEgULUQhpNVAEC9uKLLz70EP/PTTfddO7++++XctQjEcNJAhx99NFyr+Rwww3ndtttNylrdBSyCAErUUWCgROQPwkhKcGrL/v0008rieoUU0yRO1ENEyOsY/RtnHHGcWOPPbaM1voRamvkEmRJVPEe2A9e03j99dfl5Lv//vtrSTr+uBs5KXe7fLtjdHWqqaZy11xzjaxbtpa87TrrrMNEtcsUJqr4YYb+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Eohk58Ybb3Tnn3++PMI0Ly+88IKbfPLJ3a677qolncfyB0hPNQ0x6LwjRYSQUqExJp0oUIh6hKSErtnHBbaCd955x22yySZuvPHGcxNPPLG77LLL3Pvvv+8efPBBt8ACC7iRRx7ZLb/88u6+++7TLQbz5ZdfusUWW0z20whhuzz99NNuiimmkGTVU3S73XPPPXLC/cc//qEl9dl0003lMyIp7weytKllk/W7KPo7A1ZCApHsoI/OP//87tNPP9WS7Lz88stu1llndfvuu6+WdB7LHyA91TTEoPOOFBFCSoXGmHSiQCHqcnAJ/Ndff5VljEROOeWU7ne/+51bdtlluzbBeeaZZ9xss83mDj/8cC2pBSMw0047rbvwwgu1ZDDNJqoA7bblllu60Ucf3U0zzTRu3HHHdUsssYRcaiwaJN14j3/9619aUp9+S1TBgQce6MYZZxxJ2qeaair5gTDaaKO57bffPjXRPOKII9yYY47pJp10UtkOfg5NMMEE8nrDDTeoZbFYCQlEsrP55pu7hRdeuKHL9z5R3XvvvbXEuV9++UX6bit+mGTB8gdITzUNMei8I0WEkFKhMSadKFCIuhQEagRxBPBRRx3VDTPMMJJw4aQ91lhjuRVWWKErE5yNNtpITjz+MmB8sgnX1113Xbm8j6Q0ppFEFSM6d955p7v77rslYVxppZXcH//4R7ntwPPNN9+4jTfe2O2yyy7ujjvukKQZlx8t0k6UYd2bb74piRZGj//617/K/nCyrUc/Jaq4zWPVVVd1V199tZZUQfvPNNNMksCivS322WcfN/vss7sPPvhASwbTisTFSkggkp1mEtVXX33VzTfffG6GGWZwq6yyilt55ZXdkCFD3Oqrr+6efPJJtWovlj9AeqppiEHnHSkihJQKjTHpRIFC1KUg6ZpnHgmOMhKIezuPO+44GbUbaaSRujZR3WabbeQyYJY/QSGpXXLJJd3XX3+tJVWyJqpIjDbccEO31VZbuXnnnVfaZscdd3SPP/64WlQJEx38CDj99NPdeeedJ/fO/uUvf5HEEUksXu+//361TOapp56ShPfoo4+W2xtwLEsvvbSbe+653bfffis2aclVvySq8Wf062E52gcjpUkjo7j0ix84+F7aiZWQQCQ7m222mfixv/KThxdffNHNMsss7qCDDtKSWtL6T6uw/AEaONM0Rs05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37z6+eefZX84Hqu+UWG/jRw7bHAsW2yxhRsyZIj78MMPxV8sW6q1shISyLKlkgV/h9/HfcErKRaiH4C///3v7g9/+IN77LHHZN2yzSomqoSQrkRjTDpRoBC1kCISVZwAsJ8kIVmytuukcFzgX//6l5t55pndnHPO6eaZZ566mnfeed18883nJphgAjfllFO6Bx98UPZjvUdWgTvvvNONP/747sgjj5T1ZhJWtDdGfD799FN3/PHHu9FHH12OdYEFFpBjH3PMMeUz33777e6bb74R+zhp9cew8cYbu0UWWcR98MEHUhba9JqK8lO0i7V9WuLfjKyEBLJsqVrhO4G++uord/nll7tJJ51U+hn6ge/Lc801lxtppJHcCius4J5//nnpOz5xhbAMDj30UDfDDDO4Rx55RNat98sqJqqEkK5EY0w6UaAQtRAEYiuQ1hOCOU7s4OWXX3ZHHXWUJFnHHntsRSjDKMQTTzwhdnivZi+ZFaHw2BvllFNOcdNOO627//77Zd16nzThGDxIUjFyOd5447kll1zSnXbaaWID8raX3y9OzkhMJ5poIvle3nnnHSkHSK632WYbN9xww7k99thDS2vfC/RTogreeustd9JJJ7kDDjigogMPPFBe0Q5IZOAXVp8I2/Wcc86pbL///vvLK/z9zTffrNjk/d7SZCUkkGVLVeW/M7Dhhhu6kUceWb7nZ555RkurXH311W6ttdZyY489tltnnXUkbsE3oIMOOsgddthhbplllnGzzTabe/zxx2Ub6z2ziokqIaQr0RiTThQoRC2k0UQVfPzxx2777beXhG3UUUd1o4wyihtttNFEWB9jjDEkUcIoxCabbOI+++wz2a7Ik3gjAi+88IJbfvnl3ayzzioJXaj555/fLbroou5Pf/qTW2yxxWQ9rF9wwQXdVFNN5WafffZcoyv43Lj06HnggQdkX0gY8R5Yf/fdd911110n73vcccep5QB+H/F+vXzyff7558uxX3zxxfId4TsOR2hxksTr66+/LifiVVZZxT377LOyrbcB/Zao3nPPPW7qqad2O++8s3vxxRflBxQu40IPP/ywe+211yTJjEdW0X7grLPOklG4EUYYwa233nrSZkh+jz76aPH5KaaYwu26667uiy++EPtwH83ISkggy5aqCuA7X3bZZd0JJ5wgP9bw3Xr/98J3Di666CI31lhjiS38HQnpo48+6p588kmJF4h1uBKBMhDuI6+YqBJCuhKNMelEgULUQppJVN9//323xBJLuK233lrWAQKwD8I4kSMBw2VyXHLDyXyvvfaSOiRs1n7bJZyccJw4Dn/Mfh1cc801crn8wgsvlHVv50FyMt1002UaUf3222/lEjsuIWIkdtxxx5VLjVtttVUlCfLfAxJRX3byySfLZUpcut9hhx3cd999Jza4jAn5dS+fqOJy/zTTTCMjtSC08fLvcfDBB7sZZ5xxUMIN+jFRxY+qY445RtbD5D1Nvq3gu/hhgyQXoM6P2sE/kLwutdRSlR9k8X4alZWQQJYtVRXAjz78qDz99NNlHf3esoUA+viaa67pFl988cr3WK+vNKIwljSC5Q+QnmoaYtB5R4oIIaVCY0w6UaAQtRCfIOUVTtB+JAL4Ml///fffa41zJ554otwXiRHWfffdV8ranaji2Hwil4Vrr71WElWMSlr85z//kREWjEqGhJ8LiRA499xzZYRzpZVWciuvvLIk9hiJA/7Y/DZeKPP3xoF7771XtscoMO6lw/LNN98sdf7ky0Q1WcAnqhgxi0HbWd8D5JMKjJbix8lLL70k66jDNh4kOAsvvLDcGwzi/TQqKyGBLFuqKpA1UQ2/xzXWWEN8nokqE1VCSofGmHSiQCFqIY0mqknyJ3uAE/Y+++wjJ2+Mqv7+9793u+yyi9S1O1EFuIS36aabSkKBe9aSBBuMjCG5xiV4rIf1G2ywgZThvlIkclhH+aqrrir3svnRU5+othqcfNHuTFSTBZCoTjLJJHLLBr6/jTbayK2++urywwFXBwBs44QV7Yr2eu655+Ty/7bbbusuueQSsQe453G77baTe7LxHhhBL7JfWQkJZNlSVYGsiSq46667pB/jhwy+6xh8v/wzFSGkr9EYk04UKEQtpMgTKpJPD0ZOcbkf9+3hflVM64J7u5DAWdu2WjhBIYH45JNP3EcffST3btYTbK3yJGG/n3/+ubwfePrpp+XWhwknnFBG8tKEEyD+qDHTTDOZ9Zbw5yuMrPok0ieqOKEiIbvvvvtkPW4LJGL+RHnIIYfId/TQQw/JurcB/ZSo4vvHrRL48RR+Zyh75ZVX5J7kLbfcUj4jiJNVCGCaroUWWkh8GqOr008/vdyeASEpAv6HQ7x9o7ISEsiypaoCuIUH/e/MM8+U9bSRc8Qm/MjELTn4Pn0/w/cMob9hhgD84AXWPrKKiSohpCvRGJNOFChELaTZRBWBH5f5MQKx3HLLuWGGGUYu8eNePiQ4+POJv3yO4FzkCbwI+c+PS/j4DLj/MEmoxx9u8BnqtRtsfOKYBYzS4KT4z3/+U0uyEyZGePVlGMnGvXZIxLCOHxI4bnxfSKpwAvf3DAO/Dwj0U6KapPB7Ou+88+T+4SuuuELWUe/9+7333pM/YWGE3d+2EYOZFPDHnaeeekoSYGwbv18jshISyLKlqvJ9AcCPkWziD4uoQyyCf+MV3xN+wKDv4Qe1v6UmBrNncESVENLXaIxJJwoUohbSaKKKk4C/tI3LoP7f/vhX/H777SdTVnkwUhEmQZ0WjgWfG2AkEf9832233SQRwa0JSUI97lPElES4ZxQg+cvy2XyiiJMc/iSFhNePLgNcdkSi6v/p30ySg/fByBD+xYz7WTGrwLrrritzxmIaJcwHiz9o4R5bXKqGffx+oAyJKoTvBuCyPi4TYxQOoA5gOi/MXoHRZxB/534ZwBajcZjeCBSRrFoJCWTZUrVCP8d3cOONN7o///nPbsQRR5TbenB7jJ9SD98V/qyIHyqe8Pv1sYL3qBJC+h6NMelEgULUQhpNVAEuje+0005ujjnmkMvHSFT/8pe/SF0aWRK7VgrgDzFrr72223vvveUSvf/zF04gSQI4doysIrnFny6wLbDeJxROlgD3v0022WTu1ltvlXXUgdtuu00uLR5++OGyjiQx3kdeIRHGH0JwywVmJwiFGRlgg6Qr3g7yx9AviSq+N59whD+c8Oq/G0zrhXk0MZ8qQD1A8onR5yyJKn744HtkotpdwneOW39w2d73AYyu4gcnvjPMouF/OMZiokoIKQ0aY9KJAoWohTSTqCJ5weV+zD2If8hDSFiRiMXCPZO4JQB/rgJJCVI7BHDCwj2hGB0FWRNDn9QcccQRcj8pTnbAsg3lt8OE85jLE4kp8PUY1cMxFJHYFCHQT4kquPvuu2XEFN8dQIIJMHctPiPm+oVfgnBbn1TAd3FLi79HEZf3IdTjFRPG43GzX375pdSH+2hGVkICWbZU8WKiSggpDRpj0okChaiFNDuiuueee8qUS+uvv36qcOkZ/4rHnxqQDDT6vkUICYpPSHC5D1M+nX322e6OO+5wN9xwQ6LwyNELLrhA/sD073//W7YH4ehaksJEFZeRkSzhsrv1PmnCZWmMAOE9ixh1TRLA/jE3KB4z2Q+JKh6PiRF/3EeKH1j43nEPL3zTP7kLttb36ZNajMphlgD8+QrbQ7iUjFefwOBHRxafyCorIYEsW6p4+UQVP2rxQwcPhwCWbVYxUSWEdCUaY9KJAoWohTSaMOJE7O/ty0MnR1Jj+eQDnwOXe//xj39IApok1ON+XH+bgLXPJOE9cHLCE24wryr2d+qppw56j3rCMeCPUDiGVib7SFJxzEjO8XjJr7/+Wo7fsu0F4bv2PxYsUFcvuazn82izevtoRFZCAlm2VPHyfRe30OCPofjR1mwcY6JKCOlKNMakEwUKUQvp5MhmNwknIyQreE2Sr7e2zyq/n3rvlaQijiGP/PtadVR7ZCUkkGVLtU5F9gUmqoSQrkRjTDpRoBC1ECaqFNXdshISyLKlekNMVAkhXYnGmHSiQCFqIUxUKaq7ZSUkkGVL9YaYqBJCuhKNMelEgULUQpioUlR3y0pIIMuW6g0xUSWEdCUaY9KJAoWohTBRpajulpWQQJYt1RtiokoI6Uo0xqQTBQpRC2GiSlHdLSshgSxbqjfERJUQ0pVojEknChSiFsJElaK6W1ZCAlm2VG+IiSohpCvRGJNOFChELQSJKuZ+bMX8jxRFNS8rIYEsW6q75eMsE1VCSFeiMSadKFCICCGlxUpIIFJeLH+A9FTTEIPOO1JECCkVGmPSiQKFiBBSWqyEBCLlxfIHSE81DTHovCNFhJBSoTEmnShQiAghpcVKSCBSXix/gPRU0xCDzjtSRAgpFRpj0okChYgQUlqshAQi5cXyB0hPNQ0x6LwjRYSQUqExJp0oUIgIIaXFSkggUl4sf4D0VNMQg847UkQIKRUaY9KJAoWIEFJarIQEIuXF8gdITzUNMei8I0WEEBIRBwpIqwghJcRKSCCtJiXE8gdIqxvCn29CaRUhhFSJAwWkVYSQEmIlJJBWkxJi+QOk1Q3hzzehtIoQQqrEgQLSKkJICbESEkirSQmx/AHS6obw55tQWkUIIVXiQAFpFSGkhFgJCaTVpIRY/gBpdUP4800orSKEkCpxoIC0ihBSQqyEBNJqUkIsf4C0uiH8+SaUVhFCSJU4UEBaRQgpIVZCAmk1KSGWP0Ba3RD+fBNKqwghpEocKCiKKreshASybKlyyPIHyLJtRnpaIoSQKnGgoCiq3LISEsiypcohyx8gy7YZ6WmJEEKqxIGCoqhyy0pIIMuWKocsf4As22akpyVCCCGEEBsrIYG0mpQQyx8grSaEEEIIaQ9WQgJpNSkhlj9AWk0IIYQQ0h6shATSalJCLH+AtJoQQgghpD1YCQmk1aSEWP4AaTUhhBBCSHuwEhJIq0kJsfwB0mpCCCGEkPZgJSSQVpMSYvkDpNWEEEIIIe3BSkggrSYlxPIHSKsJIYQQQtqDlZBAWk1KiOUPkFYTQgghhLQHKyGBtJqUEMsfIK0mhBBCCGkPVkICaTUpIZY/QFpNCCGEENIerIQE0mpSQix/gLSaEEIIIaQ9WAkJpNWkhFj+AGk1IYQQQkh7sBISSKtJCbH8AdJqQgghhJD2YCUkkFaTEmL5A6TVhBBCCCHtwUpIIK0mJcTyB0irCSGEEELag5WQQFpNSojlD5BWE0IIIYS0ByshgbSalBDLHyCtJoQQQghpD1ZCAmk1KSGWP0BaTQghhBDSHqyEBNJqUkIsf4C0mhBCCCGkPVgJCaTVpIRY/gBpNSGEEEJIe7ASEkirSQmx/AHSakIIIYSQ9mAlJJBWkxJi+QOk1YQQQggh7cFKSCCtJiXE8gdIqwkhhBBC2oOVkEBaTUqI5Q+QVhNCCCGEtAcrIYG0mpQQyx8grSaEEEIIaQ9WQgJpNSkhlj9AWk0IIYQQ0h6shATSalJCLH+AtJoQQgghpD1YCQmk1aSEWP4AaTUhhBBCSHuwEhJIq0kJsfwB0mpCCCGEkPZgJSSQVpMSYvkDpNWEEEIIIe3BSkgoypK6DCGEEEJIe7ASEoqypC5DCCGEENIerISEoiypyxBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGdwCUoL81sSwghhBBCiBAmlVmUhbz2hBBCCCGEVAiTySwJZWyfVc1Q1H46QS8fe7fBtiSEEEJKRDMn/nDbLGqEZrfvBvrhM3QbbFNCCCGkBDRzws+ybRabJJrZtpvol8/RbbBdCSGEkD6nmZN9lm2z2Fg0ul030k+fpdtg2xJCCCF9TiMn+3CbrMpKI9vEhPuIlRVrW688ZNkui01Mlm2SbMJyqz4mr31I2jZhXZJNPZrZlhBCCCE9QHiyTzvhx3Z5lJVmt8miJCzbeqpHFtssNjFZtoltwvU0Aas8SWnEduF6PWUhrz0hhBBCepTwpF9PWWi1PQi3ybNdSCP7yLpNUTYxWbYJbRqxhZJo1C7NFuSx9eS1J4QQQgjJTd6EI6+9RbiPvPvJsm29epDFJibLNllsQlphn8UmJu82ee0JIYQQ0qOEJ/0ilYU89nls02h2P/W2r1cPstjEZNkmi01IK+yz2MTk3SavPSGEEEJ6lPCkX6SykMc+j20aze6n3vb16kEWm5gs22SxCWmFfRabmLzb5LUnhBBCCMmdQOSxz2ObRrP7qbd9vXqQxSYmyzZZbEJaYZ/FJibvNnntCSGEENKjhCf9IpWFvNvksU2j0f1k2S6vTZqdJ6t9FpuQVthnsYnJs01om8WeEEIIIT1Mp0/6ed8/tM+yXVJ9vI9m7TyN2CXZxjZeSWSxCWmFfRabmDzb5LElhBBCSI/TDSf+Ro4h3Kae0rDsk5SFPPahbZI8VllMFpuQVthnsYnJuk1WO0IIIYT0CeHJv2hlpZFtSPmgnxBCCCGkI4RJCBMREkLfIIQQQkhXwISEhNAfCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghhBBCCCGEEEIIIYQQQgghneL//u//A+RdzvG8z/lgAAAAAElFTkSuQmCC)  \n",
        "\n",
        "+ Data Frame의 각 열(column)은 Series 입니다.\n",
        "+ Series가 모여 Data Frame이 됩니다.\n"
      ],
      "metadata": {
        "id": "JX8H916XZq8g"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "df['나이']\n",
        "\n",
        "#series_temp = df['나이']\n",
        "#print(type(series_temp))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "B62LnefwaYNx",
        "outputId": "a3063bfc-c85b-44ae-97a7-a2f9fc7bdccc"
      },
      "execution_count": 23,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "0    22\n",
              "1    35\n",
              "2    58\n",
              "Name: 나이, dtype: int64"
            ]
          },
          "metadata": {},
          "execution_count": 23
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "+ Data Frame의 각 열을 선택할 때, 대괄호[]를 사용.\n",
        "+ 각 열의 데이터 타입이 Series라는 것을 확인할 수 있습니다."
      ],
      "metadata": {
        "id": "fH0yjz8NbSoC"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "ages = pd.Series([22,35,58], name='나이')\n",
        "ages\n"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "GZ4IjCxtcEMw",
        "outputId": "66b666ef-c625-4282-dffe-4976f2e4b8b2"
      },
      "execution_count": 24,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "0    22\n",
              "1    35\n",
              "2    58\n",
              "Name: 나이, dtype: int64"
            ]
          },
          "metadata": {},
          "execution_count": 24
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "+ series : 단열 열이므로 열 레이블이 없고, 행 라벨이 있음.\n",
        "+ int64 : 정수형 데이터 타입"
      ],
      "metadata": {
        "id": "cC9VsPNvcUyA"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "## 3. Data Frame 또는 Series를 이용한 작업\n",
        "\n",
        "+ mas() : 최대값을 출력"
      ],
      "metadata": {
        "id": "MeMO7KvUcyTR"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "df['Age'].max()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "xjhYuwaXdAzZ",
        "outputId": "087c201d-aac8-4b9f-8753-a12c927a9f89"
      },
      "execution_count": 19,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "58"
            ]
          },
          "metadata": {},
          "execution_count": 19
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "ages.max()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "QlF49If_dtA3",
        "outputId": "fc9b8d81-e1b7-411e-8f23-642d57fba519"
      },
      "execution_count": 25,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "58"
            ]
          },
          "metadata": {},
          "execution_count": 25
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import pandas as pd\n",
        "\n",
        "passenger = {\"이름\" : [\"홍길동\", \"이순신\", \"콩순이\"],\n",
        "             \"나이\" : [22, 35, 58], \n",
        "             \"성별\" : [\"남\", \"남\", \"여\"],\n",
        "             }\n",
        "#print(passenger['name'][0])\n",
        "df = pd.DataFrame(data = passenger)\n",
        "df.describe()"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 300
        },
        "id": "uv8D9BMFdqs5",
        "outputId": "5dc6222f-ccbe-42cd-f3ba-0aaf1eed6953"
      },
      "execution_count": 29,
      "outputs": [
        {
          "output_type": "execute_result",
          "data": {
            "text/plain": [
              "              나이\n",
              "count   3.000000\n",
              "mean   38.333333\n",
              "std    18.230012\n",
              "min    22.000000\n",
              "25%    28.500000\n",
              "50%    35.000000\n",
              "75%    46.500000\n",
              "max    58.000000"
            ],
            "text/html": [
              "\n",
              "  <div id=\"df-d303e37f-e2db-4ad5-913d-69623daaa5db\">\n",
              "    <div class=\"colab-df-container\">\n",
              "      <div>\n",
              "<style scoped>\n",
              "    .dataframe tbody tr th:only-of-type {\n",
              "        vertical-align: middle;\n",
              "    }\n",
              "\n",
              "    .dataframe tbody tr th {\n",
              "        vertical-align: top;\n",
              "    }\n",
              "\n",
              "    .dataframe thead th {\n",
              "        text-align: right;\n",
              "    }\n",
              "</style>\n",
              "<table border=\"1\" class=\"dataframe\">\n",
              "  <thead>\n",
              "    <tr style=\"text-align: right;\">\n",
              "      <th></th>\n",
              "      <th>나이</th>\n",
              "    </tr>\n",
              "  </thead>\n",
              "  <tbody>\n",
              "    <tr>\n",
              "      <th>count</th>\n",
              "      <td>3.000000</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>mean</th>\n",
              "      <td>38.333333</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>std</th>\n",
              "      <td>18.230012</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>min</th>\n",
              "      <td>22.000000</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>25%</th>\n",
              "      <td>28.500000</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>50%</th>\n",
              "      <td>35.000000</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>75%</th>\n",
              "      <td>46.500000</td>\n",
              "    </tr>\n",
              "    <tr>\n",
              "      <th>max</th>\n",
              "      <td>58.000000</td>\n",
              "    </tr>\n",
              "  </tbody>\n",
              "</table>\n",
              "</div>\n",
              "      <button class=\"colab-df-convert\" onclick=\"convertToInteractive('df-d303e37f-e2db-4ad5-913d-69623daaa5db')\"\n",
              "              title=\"Convert this dataframe to an interactive table.\"\n",
              "              style=\"display:none;\">\n",
              "        \n",
              "  <svg xmlns=\"http://www.w3.org/2000/svg\" height=\"24px\"viewBox=\"0 0 24 24\"\n",
              "       width=\"24px\">\n",
              "    <path d=\"M0 0h24v24H0V0z\" fill=\"none\"/>\n",
              "    <path d=\"M18.56 5.44l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94zm-11 1L8.5 8.5l.94-2.06 2.06-.94-2.06-.94L8.5 2.5l-.94 2.06-2.06.94zm10 10l.94 2.06.94-2.06 2.06-.94-2.06-.94-.94-2.06-.94 2.06-2.06.94z\"/><path d=\"M17.41 7.96l-1.37-1.37c-.4-.4-.92-.59-1.43-.59-.52 0-1.04.2-1.43.59L10.3 9.45l-7.72 7.72c-.78.78-.78 2.05 0 2.83L4 21.41c.39.39.9.59 1.41.59.51 0 1.02-.2 1.41-.59l7.78-7.78 2.81-2.81c.8-.78.8-2.07 0-2.86zM5.41 20L4 18.59l7.72-7.72 1.47 1.35L5.41 20z\"/>\n",
              "  </svg>\n",
              "      </button>\n",
              "      \n",
              "  <style>\n",
              "    .colab-df-container {\n",
              "      display:flex;\n",
              "      flex-wrap:wrap;\n",
              "      gap: 12px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert {\n",
              "      background-color: #E8F0FE;\n",
              "      border: none;\n",
              "      border-radius: 50%;\n",
              "      cursor: pointer;\n",
              "      display: none;\n",
              "      fill: #1967D2;\n",
              "      height: 32px;\n",
              "      padding: 0 0 0 0;\n",
              "      width: 32px;\n",
              "    }\n",
              "\n",
              "    .colab-df-convert:hover {\n",
              "      background-color: #E2EBFA;\n",
              "      box-shadow: 0px 1px 2px rgba(60, 64, 67, 0.3), 0px 1px 3px 1px rgba(60, 64, 67, 0.15);\n",
              "      fill: #174EA6;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert {\n",
              "      background-color: #3B4455;\n",
              "      fill: #D2E3FC;\n",
              "    }\n",
              "\n",
              "    [theme=dark] .colab-df-convert:hover {\n",
              "      background-color: #434B5C;\n",
              "      box-shadow: 0px 1px 3px 1px rgba(0, 0, 0, 0.15);\n",
              "      filter: drop-shadow(0px 1px 2px rgba(0, 0, 0, 0.3));\n",
              "      fill: #FFFFFF;\n",
              "    }\n",
              "  </style>\n",
              "\n",
              "      <script>\n",
              "        const buttonEl =\n",
              "          document.querySelector('#df-d303e37f-e2db-4ad5-913d-69623daaa5db button.colab-df-convert');\n",
              "        buttonEl.style.display =\n",
              "          google.colab.kernel.accessAllowed ? 'block' : 'none';\n",
              "\n",
              "        async function convertToInteractive(key) {\n",
              "          const element = document.querySelector('#df-d303e37f-e2db-4ad5-913d-69623daaa5db');\n",
              "          const dataTable =\n",
              "            await google.colab.kernel.invokeFunction('convertToInteractive',\n",
              "                                                     [key], {});\n",
              "          if (!dataTable) return;\n",
              "\n",
              "          const docLinkHtml = 'Like what you see? Visit the ' +\n",
              "            '<a target=\"_blank\" href=https://colab.research.google.com/notebooks/data_table.ipynb>data table notebook</a>'\n",
              "            + ' to learn more about interactive tables.';\n",
              "          element.innerHTML = '';\n",
              "          dataTable['output_type'] = 'display_data';\n",
              "          await google.colab.output.renderOutput(dataTable, element);\n",
              "          const docLink = document.createElement('div');\n",
              "          docLink.innerHTML = docLinkHtml;\n",
              "          element.appendChild(docLink);\n",
              "        }\n",
              "      </script>\n",
              "    </div>\n",
              "  </div>\n",
              "  "
            ]
          },
          "metadata": {},
          "execution_count": 29
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "+ count : 열의 개수\n",
        "+ mean : 평균\n",
        "+ std : 표준편차\n",
        "+ min : 최소값\n",
        "+ max : 최대값\n",
        "+ 25% / 50% / 75% : 백분위수의 각 지점, 분포를 반영해 평균을 보완하는 목적으로 사용.\n",
        "+ 25% : 하위 백분위수\n",
        "+ 75% : 상위 백분위수\n",
        "+ 50% : 중위수"
      ],
      "metadata": {
        "id": "TVaGuwEwew0x"
      }
    },
    {
      "cell_type": "markdown",
      "source": [
        "## 정리\n",
        "\n",
        "+ pandas 패키지 : `import pandas as pd`\n",
        "+ pandas의 데이터 테이블 : `DataFrame`\n",
        "+ DataFrame의 각 열(컬럼 : column)은 Series\n",
        "+ DataFrame 또는 Series에 메소드(max(), min() 등)를 적용 가능.\n"
      ],
      "metadata": {
        "id": "4D4BALqVgGny"
      }
    }
  ]
}