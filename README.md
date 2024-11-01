# This is a basic workflow to help you get started with Actions

name: CI

# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but only for the "main" branch
  push:
    branches: [ "main" ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  try:
    uses: ./.github/workflows/outsider.yaml

  build:
    # The type of runner that the job will run on
    runs-on: ubuntu-latest

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v4

      - name: MarcosAntonioCortesRuiz?
        run: echo ${{ github.actor }}

  update-tag:southunitedraza
    needs: build 

    runs-on: ubuntu-latest

    steps:
      - uses: actions/checkout@v4

      - name: Update logs with date
        run: date >> logs

      - name: Create Pull Request
        id: cpr
        uses: peter-evans/create-pull-request@v6
        with:
          commit-message: "github-action[bot] Update logs"
          add-paths: "logs"
          branch: github-action/auto-merge
          delete-branch: true
          branch-suffix: random
      - name: Enable Pull Request Automerge
        run: gh pr merge "${{ steps.cpr.outputs.pull-request-number }}" --squash --auto 
        env:
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      - name: Approve the PR
        run: gh pr review "${{ steps.cpr.outputs.pull-request-number }}" --approve
        env:
          GH_TOKEN: ${{ secrets.TMP_APPROVER_PAT }}t.me/southunitedraza
{"constructors":[{"id":"528568095","predicate":"decryptedMessage","params":[{"name":"random_id","type":"long"},{"name":"random_bytes","type":"bytes"},{"name":"message","type":"string"},{"name":"media","type":"DecryptedMessageMedia"}],"type":"DecryptedMessage","layer":8},{"id":"541931640","predicate":"decryptedMessage","params":[{"name":"random_id","type":"long"},{"name":"ttl","type":"int"},{"name":"message","type":"string"},{"name":"media","type":"DecryptedMessageMedia"}],"type":"DecryptedMessage","layer":17},{"id":"917541342","predicate":"decryptedMessage","params":[{"name":"flags","type":"#"},{"name":"random_id","type":"long"},{"name":"ttl","type":"int"},{"name":"message","type":"string"},{"name":"media","type":"flags.9?DecryptedMessageMedia"},{"name":"entities","type":"flags.7?Vector<MessageEntity>"},{"name":"via_bot_name","type":"flags.11?string"},{"name":"reply_to_random_id","type":"flags.3?long"}],"type":"DecryptedMessage","layer":45},{"id":"-1848883596","predicate":"decryptedMessage","params":[{"name":"flags","type":"#"},{"name":"random_id","type":"long"},{"name":"ttl","type":"int"},{"name":"message","type":"string"},{"name":"media","type":"flags.9?DecryptedMessageMedia"},{"name":"entities","type":"flags.7?Vector<MessageEntity>"},{"name":"via_bot_name","type":"flags.11?string"},{"name":"reply_to_random_id","type":"flags.3?long"},{"name":"grouped_id","type":"flags.17?long"}],"type":"DecryptedMessage","layer":73},{"id":"-1438109059","predicate":"decryptedMessageService","params":[{"name":"random_id","type":"long"},{"name":"random_bytes","type":"bytes"},{"name":"action","type":"DecryptedMessageAction"}],"type":"DecryptedMessage","layer":8},{"id":"1930838368","predicate":"decryptedMessageService","params":[{"name":"random_id","type":"long"},{"name":"action","type":"DecryptedMessageAction"}],"type":"DecryptedMessage","layer":17},{"id":"144661578","predicate":"decryptedMessageMediaEmpty","params":[],"type":"DecryptedMessageMedia","layer":8},{"id":"846826124","predicate":"decryptedMessageMediaPhoto","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"w","type":"int"},{"name":"h","type":"int"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"}],"type":"DecryptedMessageMedia","layer":8},{"id":"-235238024","predicate":"decryptedMessageMediaPhoto","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"w","type":"int"},{"name":"h","type":"int"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"},{"name":"caption","type":"string"}],"type":"DecryptedMessageMedia","layer":45},{"id":"1290694387","predicate":"decryptedMessageMediaVideo","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"duration","type":"int"},{"name":"w","type":"int"},{"name":"h","type":"int"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"}],"type":"DecryptedMessageMedia","layer":8},{"id":"1380598109","predicate":"decryptedMessageMediaVideo","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"duration","type":"int"},{"name":"mime_type","type":"string"},{"name":"w","type":"int"},{"name":"h","type":"int"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"}],"type":"DecryptedMessageMedia","layer":17},{"id":"-1760785394","predicate":"decryptedMessageMediaVideo","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"duration","type":"int"},{"name":"mime_type","type":"string"},{"name":"w","type":"int"},{"name":"h","type":"int"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"},{"name":"caption","type":"string"}],"type":"DecryptedMessageMedia","layer":45},{"id":"893913689","predicate":"decryptedMessageMediaGeoPoint","params":[{"name":"lat","type":"double"},{"name":"long","type":"double"}],"type":"DecryptedMessageMedia","layer":8},{"id":"1485441687","predicate":"decryptedMessageMediaContact","params":[{"name":"phone_number","type":"string"},{"name":"first_name","type":"string"},{"name":"last_name","type":"string"},{"name":"user_id","type":"int"}],"type":"DecryptedMessageMedia","layer":8},{"id":"-1586283796","predicate":"decryptedMessageActionSetMessageTTL","params":[{"name":"ttl_seconds","type":"int"}],"type":"DecryptedMessageAction","layer":8},{"id":"-1332395189","predicate":"decryptedMessageMediaDocument","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"file_name","type":"string"},{"name":"mime_type","type":"string"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"}],"type":"DecryptedMessageMedia","layer":8},{"id":"2063502050","predicate":"decryptedMessageMediaDocument","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"mime_type","type":"string"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"},{"name":"attributes","type":"Vector<DocumentAttribute>"},{"name":"caption","type":"string"}],"type":"DecryptedMessageMedia","layer":45},{"id":"1790809986","predicate":"decryptedMessageMediaDocument","params":[{"name":"thumb","type":"bytes"},{"name":"thumb_w","type":"int"},{"name":"thumb_h","type":"int"},{"name":"mime_type","type":"string"},{"name":"size","type":"long"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"},{"name":"attributes","type":"Vector<DocumentAttribute>"},{"name":"caption","type":"string"}],"type":"DecryptedMessageMedia","layer":143},{"id":"1619031439","predicate":"decryptedMessageMediaAudio","params":[{"name":"duration","type":"int"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"}],"type":"DecryptedMessageMedia","layer":8},{"id":"1474341323","predicate":"decryptedMessageMediaAudio","params":[{"name":"duration","type":"int"},{"name":"mime_type","type":"string"},{"name":"size","type":"int"},{"name":"key","type":"bytes"},{"name":"iv","type":"bytes"}],"type":"DecryptedMessageMedia","layer":17},{"id":"206520510","predicate":"decryptedMessageActionReadMessages","params":[{"name":"random_ids","type":"Vector<long>"}],"type":"DecryptedMessageAction","layer":8},{"id":"1700872964","predicate":"decryptedMessageActionDeleteMessages","params":[{"name":"random_ids","type":"Vector<long>"}],"type":"DecryptedMessageAction","layer":8},{"id":"-1967000459","predicate":"decryptedMessageActionScreenshotMessages","params":[{"name":"random_ids","type":"Vector<long>"}],"type":"DecryptedMessageAction","layer":8},{"id":"1729750108","predicate":"decryptedMessageActionFlushHistory","params":[],"type":"DecryptedMessageAction","layer":8},{"id":"467867529","predicate":"decryptedMessageLayer","params":[{"name":"random_bytes","type":"bytes"},{"name":"layer","type":"int"},{"name":"in_seq_no","type":"int"},{"name":"out_seq_no","type":"int"},{"name":"message","type":"DecryptedMessage"}],"type":"DecryptedMessageLayer","layer":17},{"id":"381645902","predicate":"sendMessageTypingAction","params":[],"type":"SendMessageAction","layer":17},{"id":"-44119819","predicate":"sendMessageCancelAction","params":[],"type":"SendMessageAction","layer":17},{"id":"-1584933265","predicate":"sendMessageRecordVideoAction","params":[],"type":"SendMessageAction","layer":17},{"id":"-1845219337","predicate":"sendMessageUploadVideoAction","params":[],"type":"SendMessageAction","layer":17},{"id":"-718310409","predicate":"sendMessageRecordAudioAction","params":[],"type":"SendMessageAction","layer":17},{"id":"-424899985","predicate":"sendMessageUploadAudioAction","params":[],"type":"SendMessageAction","layer":17},{"id":"-1727382502","predicate":"sendMessageUploadPhotoAction","params":[],"type":"SendMessageAction","layer":17},{"id":"-1884362354","predicate":"sendMessageUploadDocumentAction","params":[],"type":"SendMessageAction","layer":17},{"id":"393186209","predicate":"sendMessageGeoLocationAction","params":[],"type":"SendMessageAction","layer":17},{"id":"1653390447","predicate":"sendMessageChooseContactAction","params":[],"type":"SendMessageAction","layer":17},{"id":"1360072880","predicate":"decryptedMessageActionResend","params":[{"name":"start_seq_no","type":"int"},{"name":"end_seq_no","type":"int"}],"type":"DecryptedMessageAction","layer":17},{"id":"-217806717","predicate":"decryptedMessageActionNotifyLayer","params":[{"name":"layer","type":"int"}],"type":"DecryptedMessageAction","layer":17},{"id":"-860719551","predicate":"decryptedMessageActionTyping","params":[{"name":"action","type":"SendMessageAction"}],"type":"DecryptedMessageAction","layer":17},{"id":"-204906213","predicate":"decryptedMessageActionRequestKey","params":[{"name":"exchange_id","type":"long"},{"name":"g_a","type":"bytes"}],"type":"DecryptedMessageAction","layer":20},{"id":"1877046107","predicate":"decryptedMessageActionAcceptKey","params":[{"name":"exchange_id","type":"long"},{"name":"g_b","type":"bytes"},{"name":"key_fingerprint","type":"long"}],"type":"DecryptedMessageAction","layer":20},{"id":"-586814357","predicate":"decryptedMessageActionAbortKey","params":[{"name":"exchange_id","type":"long"}],"type":"DecryptedMessageAction","layer":20},{"id":"-332526693","predicate":"decryptedMessageActionCommitKey","params":[{"name":"exchange_id","type":"long"},{"name":"key_fingerprint","type":"long"}],"type":"DecryptedMessageAction","layer":20},{"id":"-1473258141","predicate":"decryptedMessageActionNoop","params":[],"type":"DecryptedMessageAction","layer":20},{"id":"1815593308","predicate":"documentAttributeImageSize","params":[{"name":"w","type":"int"},{"name":"h","type":"int"}],"type":"DocumentAttribute","layer":23},{"id":"297109817","predicate":"documentAttributeAnimated","params":[],"type":"DocumentAttribute","layer":23},{"id":"-83208409","predicate":"documentAttributeSticker","params":[],"type":"DocumentAttribute","layer":23},{"id":"978674434","predicate":"documentAttributeSticker","params":[{"name":"alt","type":"string"},{"name":"stickerset","type":"InputStickerSet"}],"type":"DocumentAttribute","layer":45},{"id":"1494273227","predicate":"documentAttributeVideo","params":[{"name":"duration","type":"int"},{"name":"w","type":"int"},{"name":"h","type":"int"}],"type":"DocumentAttribute","layer":23},{"id":"250621158","predicate":"documentAttributeVideo","params":[{"name":"flags","type":"#"},{"name":"duration","type":"int"},{"name":"w","type":"int"},{"name":"h","type":"int"}],"type":"DocumentAttribute","layer":66},{"id":"85215461","predicate":"documentAttributeAudio","params":[{"name":"duration","type":"int"}],"type":"DocumentAttribute","layer":23},{"id":"-556656416","predicate":"documentAttributeAudio","params":[{"name":"duration","type":"int"},{"name":"title","type":"string"},{"name":"performer","type":"string"}],"type":"DocumentAttribute","layer":45},{"id":"-1739392570","predicate":"documentAttributeAudio","params":[{"name":"flags","type":"#"},{"name":"duration","type":"int"},{"name":"title","type":"flags.0?string"},{"name":"performer","type":"flags.1?string"},{"name":"waveform","type":"flags.2?bytes"}],"type":"DocumentAttribute","layer":46},{"id":"358154344","predicate":"documentAttributeFilename","params":[{"name":"file_name","type":"string"}],"type":"DocumentAttribute","layer":23},{"id":"236446268","predicate":"photoSizeEmpty","params":[{"name":"type","type":"string"}],"type":"PhotoSize","layer":23},{"id":"2009052699","predicate":"photoSize","params":[{"name":"type","type":"string"},{"name":"location","type":"FileLocation"},{"name":"w","type":"int"},{"name":"h","type":"int"},{"name":"size","type":"int"}],"type":"PhotoSize","layer":23},{"id":"-374917894","predicate":"photoCachedSize","params":[{"name":"type","type":"string"},{"name":"location","type":"FileLocation"},{"name":"w","type":"int"},{"name":"h","type":"int"},{"name":"bytes","type":"bytes"}],"type":"PhotoSize","layer":23},{"id":"2086234950","predicate":"fileLocationUnavailable","params":[{"name":"volume_id","type":"long"},{"name":"local_id","type":"int"},{"name":"secret","type":"long"}],"type":"FileLocation","layer":23},{"id":"1406570614","predicate":"fileLocation","params":[{"name":"dc_id","type":"int"},{"name":"volume_id","type":"long"},{"name":"local_id","type":"int"},{"name":"secret","type":"long"}],"type":"FileLocation","layer":23},{"id":"-90853155","predicate":"decryptedMessageMediaExternalDocument","params":[{"name":"id","type":"long"},{"name":"access_hash","type":"long"},{"name":"date","type":"int"},{"name":"mime_type","type":"string"},{"name":"size","type":"int"},{"name":"thumb","type":"PhotoSize"},{"name":"dc_id","type":"int"},{"name":"attributes","type":"Vector<DocumentAttribute>"}],"type":"DecryptedMessageMedia","layer":23},{"id":"-1148011883","predicate":"messageEntityUnknown","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"-100378723","predicate":"messageEntityMention","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"1868782349","predicate":"messageEntityHashtag","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"1827637959","predicate":"messageEntityBotCommand","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"1859134776","predicate":"messageEntityUrl","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"1692693954","predicate":"messageEntityEmail","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"-1117713463","predicate":"messageEntityBold","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"-2106619040","predicate":"messageEntityItalic","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"681706865","predicate":"messageEntityCode","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":45},{"id":"1938967520","predicate":"messageEntityPre","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"},{"name":"language","type":"string"}],"type":"MessageEntity","layer":45},{"id":"1990644519","predicate":"messageEntityTextUrl","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"},{"name":"url","type":"string"}],"type":"MessageEntity","layer":45},{"id":"-2044933984","predicate":"inputStickerSetShortName","params":[{"name":"short_name","type":"string"}],"type":"InputStickerSet","layer":45},{"id":"-4838507","predicate":"inputStickerSetEmpty","params":[],"type":"InputStickerSet","layer":45},{"id":"-1978796689","predicate":"decryptedMessageMediaVenue","params":[{"name":"lat","type":"double"},{"name":"long","type":"double"},{"name":"title","type":"string"},{"name":"address","type":"string"},{"name":"provider","type":"string"},{"name":"venue_id","type":"string"}],"type":"DecryptedMessageMedia","layer":45},{"id":"-452652584","predicate":"decryptedMessageMediaWebPage","params":[{"name":"url","type":"string"}],"type":"DecryptedMessageMedia","layer":45},{"id":"-1997373508","predicate":"sendMessageRecordRoundAction","params":[],"type":"SendMessageAction","layer":66},{"id":"-1150187996","predicate":"sendMessageUploadRoundAction","params":[],"type":"SendMessageAction","layer":66},{"id":"-1672577397","predicate":"messageEntityUnderline","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":101},{"id":"-1090087980","predicate":"messageEntityStrike","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":101},{"id":"34469328","predicate":"messageEntityBlockquote","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":101},{"id":"852137487","predicate":"messageEntitySpoiler","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"}],"type":"MessageEntity","layer":144},{"id":"-925956616","predicate":"messageEntityCustomEmoji","params":[{"name":"offset","type":"int"},{"name":"length","type":"int"},{"name":"document_id","type":"long"}],"type":"MessageEntity","layer":144}],"methods":[]}t.me/southunitedraza
Orlando, United States
def process_paymentout(card_number, expiry_date, cvv):


    # Validate input 


    if not is_valid_card_number(card_number):


        return "Invalid card number"





    # Encrypt sensitive data


    encrypted_card_number = encrypt(card_number)


    


    # Send payment request to gateway


    response = payment_gateway.charge(encrypted_card_number, expiry_date, cvv, amount)





    if response.success:


        # Update user account


        update_user_payment_status(user_id, "paid")


        return "Payment successful"


    else:


        return "Payment failed"
