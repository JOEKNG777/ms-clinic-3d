# MSクリニック 包茎手術説明モデル：医学監修用設計メモ v1
作成日：2026-11-10。これは患者説明用の教育コンテンツ設計であり、手術手技マニュアルではない。以下は一次資料・専門家向け総説の初期調査に基づく。網羅的システマティックレビューではない。

## 根拠資料
1. WHO (2018) Manual for male circumcision under local anaesthesia and HIV prevention services for adolescent boys and men: https://www.who.int/publications/i/item/manual-for-male-circumcision-under-local-anaesthesia-and-hiv-prevention-services-for-adolescent-boys-and-men
2. Leslie et al. Circumcision, StatPearls (2024): https://www.ncbi.nlm.nih.gov/books/NBK535436/
3. BAUS, Circumcision patient information (2024): https://www.baus.org.uk/patients/information_leaflets/88/circumcision
4. NHS, Circumcision: https://www.nhs.uk/tests-and-treatments/circumcision/

## 初期調査からの設計要件
- 成人の代表的術式は sleeve resection と dorsal slit。小帯（frenulum）の処理・温存は症例および術式によって異なる。一般論をクリニック独自の「基本・精密・特別」と一対一対応させない。
- 模型の解剖要素を別パーツにする：亀頭、冠状溝、陰茎体、包皮外板、包皮内板、小帯、尿道口。陰茎背側／腹側の向きを常に示す。
- 包皮は内板と外板が折り返す構造で、単純な筒状パーツの上下移動だけでは正確に表現できない。
- 「切除予定領域」「切除後の欠損」「縫合後」を異なる状態として表現する。現行2.5Dデモの四角い空白・縫合線は解剖学的表現ではなく、臨床説明には使わない。
- アニメーション工程（仮）：①術前の状態 ②包皮を移動し解剖確認 ③切除予定範囲を提示 ④切除範囲を概念的に表示 ⑤縫合後の接合部を表示 ⑥術後の外観と一般的な経過。麻酔・止血・術後注意は別の説明カードに分ける。
- 医学文献に基づく一般的な説明とMSクリニック固有の施術・価格・アフターケアは明確に分離し、後者は院長の承認を必須とする。
- 性機能、感度、瘢痕、仕上がりの優劣を術式名だけで断定しない。合併症や代替治療の説明も設ける。
- 術後の回復期間や行動制限は資料間で異なるため、一般的目安と院内指示を混在させない。

## 次の実装の受け入れ条件
1. 3Dモデルを360度回転でき、背側・腹側と小帯が識別できる。
2. 包皮の内外板と折り返しが解剖学的に矛盾しない。
3. 術前／予定範囲／切除後／縫合後で形状が明確に変わる。
4. 3術式の違いは院長が承認した仕様にのみ基づいて実装する。
5. iPhone Safariで操作でき、画像や3Dの表示に失敗した際は説明と代替図を出す。
6. 医師の監修が終わるまでは「教育用試作・実際の術式とは異なる」と明記する。

## 院長に確認する事項
- 「基本」「精密」「特別」の正式な術式定義、切除線の位置・形状の差
- 小帯温存・形成・切除の判断と術式ごとの扱い
- 包皮内板の残存範囲と個別調整の要素
- 術後の仕上がりとして説明可能な点／保証できない点
- 院内で採用している標準的な術後説明と例外条件

## 現状
既存 index.html はCanvas 2.5Dの操作デモ。医学的正確性の担保ができるまでは、患者向け公開資料として扱わない。
