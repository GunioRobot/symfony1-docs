��14�� - Admin �W�F�l���[�^�[
=============================

�����̃A�v���P�[�V�����̓f�[�^�x�[�X�ɕۑ����ꂽ�f�[�^�Ɋ�Â��Ă���A����ɃA�N�Z�X���邽�߂̃C���^�[�t�F�C�X��񋟂��܂��Bsymfony �� Propel �܂��� Doctrine �I�u�W�F�N�g�Ɋ�Â����f�[�^����@�\��񋟂��郂�W���[���쐬�̔����^�X�N�����������܂��B�I�u�W�F�N�g���f�����K�؂ɒ�`�����̂ł���΁Asymfony �̓T�C�g�S�̂̊Ǘ��@�\ (�A�h�~�j�X�g���[�V����) �������I�ɐ������܂��B���̏͂ł́APropel �v���O�C���� Doctrine �v���O�C���ɓ��ڂ��ꂽ Admin �W�F�l���[�^�[�����������܂��B����͊��S�ȍ\���ɂ����ʂȐݒ�t�@�C���Ɉˑ�����̂ŁA���̏͂̑����� Admin �W�F�l���[�^�[�̂��܂��܂ȉ\���ɂ��Đ������܂��B

���f�������ƂɃR�[�h�𐶐�����
------------------------------

Web�A�v���P�[�V�����ɂ����āA�f�[�^�A�N�Z�X�I�y���[�V�����͂��̂悤�ɕ��ނł��܂�:

  * ���R�[�h�̍쐬
  * ���R�[�h�̌���
  * ���R�[�h�̍X�V(�ƃJ�����̏C��)
  * ���R�[�h�̍폜

�����̃I�y���[�V�����͋��ʂȂ̂ŁA���������Ƃ�����p�̗���ł��� CRUD (Create�ARetrieval�AUpdate�ADeletion) �����݂��܂��B�����̃y�[�W�͂�����1�ɊҌ��ł��܂��B���Ƃ��΃t�H�[�����̃A�v���P�[�V�����ɂ����āA�ŐV���e�̃��X�g�͌����I�y���[�V���� (retrieve) �ŁA���e�ւ̕ԓ��͍쐬�I�y���[�V���� (create) �ɑΉ����܂��B

�C�ӂ̃e�[�u���ɑ΂��� CRUD �I�y���[�V���������������{�I�ȃA�N�V�����ƃe���v���[�g�� Web �A�v���P�[�V���������ŌJ��Ԃ�����܂��Bsymfony �ɂ����āA�o�b�N�G���h�C���^�[�t�F�C�X�̏����J�����������邽�߂ɁA���f�����C���[�� CRUD �I�y���[�V�����𐶐��ł���悤�ɂ��邽�߂̏\���ȏ��������܂��B

### �f�[�^���f���̗�

���̏͑S�̂�ʂ��āA�ꗗ�\���@�\�̓V���v���ȗ�Ɋ�Â��� symfony �� Admin �W�F�l���[�^�[�̋@�\�������܂��B����ɂ����8�͂��v���o���ł��傤�B�����2�� `BlogArticle` �N���X�� `BlogComment` �N���X���܂ށA�u���O�A�v���P�[�V�����̂悭�m��ꂽ��ł��B�}14-1�ŕ`����Ă���悤�ɁA���X�g14-1�̓X�L�[�}�������܂��B

���X�g14-1 - �u���O�A�v���P�[�V������ Propel �ɂ�����X�L�[�}�̗�

    [yml]
    propel:
      blog_category:
        id:               ~
        name:             varchar(255)
      blog_author:
        id:               ~
        name:             varchar(255)
      blog_article:
        id:               ~
        title:            varchar(255)
        content:          longvarchar
        blog_author_id:   ~
        blog_category_id: ~
        is_published:     boolean
        created_at:       ~
      blog_comment:
        id:               ~
        blog_article_id:  ~
        author:           varchar(255)
        content:          longvarchar
        created_at:       ~

�}14-1 �f�[�^���f���̗�

![�f�[�^���f���̗�](http://www.symfony-project.org/images/book/1_4/F1401.png "�f�[�^���f���̗�")

�R�[�h�������\�ɂ��邽�߂ɃX�L�[�}�쐬�̊��Ԃŏ]��Ȃ���΂Ȃ�Ȃ����ʂȃ��[���͑��݂��܂���Bsymfony �̓X�L�[�}�����̂܂܎g���A�Ǘ���ʂ𐶐����邽�߂ɃX�L�[�}�̑��������߂��܂��B

>**TIP**
>���̏͂��ő���Ɋ��p����ɂ́A��Ŏ����̓��e�����ۍ\�z���Ď������Ƃ��������߂��܂��B���X�g�Ő������ꂽ���ׂẴX�e�b�v�𒭂߂�̂ł���΁Asymfony �����𐶐����A�������ꂽ�R�[�h�ŉ����s����̂��Ƃ������Ƃ���藝���ł���悤�ɂȂ�܂��B���f���̏������́A���̂悤�� `propel:build` �^�X�N�����s���邾���Ȃ̂ŊȒP�ł�:
>
>      $ php symfony propel:build --all --no-confirmation

�������ꂽ�Ǘ��C���^�[�t�F�C�X�́A��Ƃ��y�ɂȂ�悤�ɂ������̃}�W�b�N���\�b�h�Ɉˑ����Ă��܂��B���̂悤�Ɋe���f���N���X�� `__toString()` ���\�b�h������Ă��������B

    [php]
    class BlogAuthor extends BaseBlogAuthor
    {
      public function __toString()
      {
        return $this->getName();
      }
    }

    class BlogCategory extends BaseBlogCategory
    {
      public function __toString()
      {
        return $this->getName();
      }
    }

    class BlogArticle extends BaseBlogArticle
    {
      public function __toString()
      {
        return $this->getTitle();
      }
    }


�Ǘ����
--------

symfony �́A�o�b�N�G���h�A�v���P�[�V�����̂��߂ɁA`schema.yml` �t�@�C������̃��f���N���X��`�Ɋ�Â��āA���W���[�����쐬�ł��܂��B�������ꂽ Admin ���W���[��������p���ăT�C�g�S�̂̊Ǘ���ʂ��쐬�ł��܂��B���̃Z�N�V�����̗�ł́A`backend` �A�v���P�[�V�����ɒǉ������ Admin ���W���[����������܂��B�v���W�F�N�g�� `backend` �A�v���P�[�V�����������Ȃ��ꍇ�A`generate:app` �^�X�N���Ăяo���ăX�P���g�����쐬���܂�:

    $ php symfony generate:app backend

Admin ���W���[���� `generator.yml` �Ƃ������O�̓��ʂȐݒ�t�@�C����ʂ��ă��f�������߂��܂��B���ׂĂ̐����R���|�[�l���g�ƃ��W���[���̊O�����g�����邽�߂� `generator.yml` �t�@�C����ύX�ł��܂��B���̂悤�ȃ��W���[���͒ʏ�̃��W���[�����J�j�Y������̉��b���󂯂܂� (���C�A�E�g�A���[�e�B���O�A�J�X�^���ݒ�A�I�[�g���[�h�Ȃ�)�B�Ǝ��@�\�𐶐����ꂽ�Ǘ���ʂɓ������邽�߂ɁA�������ꂽ�A�N�V�����������̓e���v���[�g���㏑�����邱�Ƃ��ł��܂����A`generator.yml` �͂����Ƃ����ʂ̗v�����l�����āAPHP �R�[�h�̎g�����������肵�܂��B

>**NOTE**
>�����Ă��̗v���� `generator.yml` �ݒ�t�@�C���ŃJ�o�[����܂����A���̏͂̌�̂ق��Ō���悤�ɁA�ݒ�N���X��ʂ��� Admin ���W���[����ݒ肷�邱�Ƃ��ł��܂��B

### Admin ���W���[��������������

���f������{�P�ʂƂ��� symfony �R�}���h�ŊǗ���ʂ��r���h���܂��B���W���[���� `propel:generate-admin` �^�X�N���g���āAPropel �I�u�W�F�N�g�܂��� Doctrine �I�u�W�F�N�g�Ɋ�Â��Đ�������܂�:

    // Propel
    $ php symfony propel:generate-admin backend BlogArticle --module=article

    // Doctrine
    $ php symfony doctrine:generate-admin backend BlogArticle --module=article

>**NOTE**
>Admin ���W���[���� REST �A�[�L�e�N�`���Ɋ�Â��Ă��܂��B`propel:generate-admin` �^�X�N�� `routing.yml` �ݒ�t�@�C���Ƀ��[�g�Ȃǂ������I�ɒǉ����܂�:
>
>     [yml]
>     # apps/backend/config/routing.yml
>     article:
>       class: sfPropelRouteCollection
>       options:
>         model:                BlogArticle
>         module:               article
>         with_wildcard_routes: true
>
>�Ǝ��̃��[�g���쐬�����f���N���X�̖��O�̑���ɓƎ��̖��O�������Ƃ��ă^�X�N�ɓn�����Ƃ��ł��܂�:
>
>     $ php symfony propel:generate-admin backend article --module=article

���̌Ăяo�������� `backend` �A�v���P�[�V�����̂Ȃ��� `BlogArticle`�N ���X�̒�`�Ɋ�Â� `article` ���W���[�����쐬�����̂ŁA���� URL ����A�N�Z�X�ł��܂�:

    http://localhost/backend.php/article

�}14-2�A�}14-3�ŕ`����Ă��鐶�����W���[���̊O���́A���p�A�v���P�[�V�����Ƃ��Ă��̂܂ܗ��p�ł���قǏ\���ɐ�������Ă��܂��B

>**TIP**
>���҂ǂ���̊O���łȂ����(�X�^�C���V�[�g�Ɖ摜���Ȃ�)�A`plugin:publish-assets` �^�X�N�����s���ăv���W�F�N�g�ɃA�Z�b�g���C���X�g�[������K�v������܂�:
>
>     $ php symfony plugin:publish-assets

�}14-2 - `backend` �A�v���P�[�V���������� `article` ���W���[���� `list` �r���[

![backend �A�v���P�[�V���������� article ���W���[���� list �r���[](http://www.symfony-project.org/images/book/1_4/F1402.png "backend �A�v���P�[�V���������� article ���W���[���� list �r���[")

�}14-3 - �o�b�N�G���h�� `article` ���W���[���� `edit` �r���[

![�o�b�N�G���h�� article ���W���[���� edit �r���[](http://www.symfony-project.org/images/book/1_4/F1403.png "�o�b�N�G���h�� article ���W���[���� edit �r���[")

### �����R�[�h������

`apps/backend/modules/article/` �f�B���N�g�����̋L���̊Ǘ���ʂ̃R�[�h�͏����������s��ꂽ�̂ŋ�Ɍ����܂��B���̃��W���[���̐����R�[�h���ᖡ���邽�߂̍ŗǂ̕��@�̓u���E�U�[�𗘗p���Ă���Ə��̂��Ƃ�����邱�Ƃ� `cache/` �t�H���_�[�̓��e���m�F���邱�Ƃł��B���X�g14-2�̓L���b�V���̂Ȃ��Ō����鐶���A�N�V�����ƃe���v���[�g�̃��X�g��\�����܂��B

���X�g14-2 - �������ꂽ�Ǘ���ʂ̗v�f (`cache/backend/ENV/modules/autoArticle/`)

    // actions/actions.class.php�̃A�N�V����
    index            // �e�[�u���̃��R�[�h�̃��X�g��\������
    filter           // ���X�g�Ŏg����t�B���^�[���X�V����
    new              // �V�������R�[�h���쐬����t�H�[����\������
    create           // �V�������R�[�h���쐬����
    edit             // ���R�[�h�̃t�B�[���h���C������t�H�[����\������
    update           // �����̃��R�[�h���X�V����
    delete           // ���R�[�h���폜����
    batch            // �I�����ꂽ���R�[�h�̃��X�g�ŃA�N�V���������s����
    batchDelete      // �I���������R�[�h�̈ꗗ���폜����A�N�V���������s����

    // templates/�̂Ȃ�
    _assets.php
    _filters.php
    _filters_field.php
    _flashes.php
    _form.php
    _form_actions.php
    _form_field.php
    _form_fieldset.php
    _form_footer.php
    _form_header.php
    _list.php
    _list_actions.php
    _list_batch_actions.php
    _list_field_boolean.php
    _list_footer.php
    _list_header.php
    _list_td_actions.php
    _list_td_batch_actions.php
    _list_td_stacked.php
    _list_td_tabular.php
    _list_th_stacked.php
    _list_th_tabular.php
    _pagination.php
    editSuccess.php
    indexSuccess.php
    newSuccess.php

����͐������ꂽ Admin ���W���[����������3�̃r���[�A`list`�A`new` �� `edit` �ō\������邱�Ƃ������܂��B�R�[�h�����Ă݂�ƁA���W���[���������ɍ����A�ǂ݂₷���g�����̂�����̂ł��邱�Ƃ��킩��܂��B

### `generator.yml` �ݒ�t�@�C������

�������ꂽ Admin ���W���[���� YAML �t�H�[�}�b�g�� `generator.yml` �ݒ�t�@�C���Ō�����p�����[�^�[�Ɉˑ����܂��B�V�����������ꂽ Admin ���W���[���̃f�t�H���g�ݒ������ɂ́A���X�g14-3�ōČ�����Ă���A`backend/modules/article/config/` �f�B���N�g���ɐݒu���ꂽ `generator.yml` �t�@�C�����J���Ă��������B

���X�g14-3 - �W�F�l���[�^�[�̃f�t�H���g�R���t�B�M�����[�V���� (`backend/modules/article/config/generator.yml`)

    [yml]
    generator:
      class: sfPropelGenerator
      param:
        model_class:           BlogArticle
        theme:                 admin
        non_verbose_templates: true
        with_show:             false
        singular:              BlogArticle
        plural:                BlogArticles
        route_prefix:          blog_article
        with_propel_route:     1
        actions_base_class:    sfActions

        config:
          actions: ~
          fields:  ~
          list:    ~
          filter:  ~
          form:    ~
          edit:    ~
          new:

���̃R���t�B�M�����[�V�����͊�{�I�ȊǗ���ʂ𐶐�����̂ɏ\���ł��B�J�X�^�}�C�Y�������e�� `config` �L�[�̉��ɒǉ�����܂��B���X�g14-4�� `generator.yml` ���J�X�^�}�C�Y�����T�^��������Ă��܂��B

���X�g14-4 - �T�^�I�ȃW�F�l���[�^�[�̑S�ݒ�

    [yml]
    generator:
      class: sfPropelGenerator
      param:
        model_class:           BlogArticle
        theme:                 admin
        non_verbose_templates: true
        with_show:             false
        singular:              BlogArticle
        plural:                BlogArticles
        route_prefix:          blog_article
        with_propel_route:     1
        actions_base_class:    sfActions

        config:
          actions:
            _new: { label: "Create a new article" }

          fields:
            author_id:    { label: Article author }
            published_on: { credentials: editor }

          list:
            title:          Articles
            display:        [title, blog_author, blog_category]
            fields:
              published_on: { date_format: dd/MM/yy }
            layout:         stacked
            params:         |
              %%is_published%%<strong>%%=title%%</strong><br /><em>by %%blog_author%%
              in %%blog_category%% (%%created_at%%)</em><p>%%content%%</p>
            max_per_page:   2
            sort:           [title, asc]

          filter:
            display: [title, blog_category_id, blog_author_id, is_published]

          form:
            display:
              "Post":       [title, blog_category_id, content]
              "Workflow":   [blog_author_id, is_published, created_at]
            fields:
              published_at: { help: "Date of publication" }
              title:        { attributes: { style: "width: 350px" } }

          new:
            title: New article

          edit:
            title: Editing article "%%title%%"

���̃R���t�B�M�����[�V�����ł́A6�̃Z�N�V����������܂��B�����̂���4�̓r���[��\�� (`list`�A`filter`�A`new` �� `edit`) �Ƃ����̂�����2�́u�o�[�`�����v(`fields` �� `form`) �Őݒ�ړI�̂��߂̂ݑ��݂��܂��B

���̃Z�N�V�����ł��̐ݒ�t�@�C���ŗ��p�\�Ȃ��ׂẴp�����[�^�[�̏ڍד��e��������܂��B

�W�F�l���[�^�[�̐ݒ�
---------------------

�W�F�l���[�^�[�̐ݒ�t�@�C���͂ƂĂ����͂ŁA�������ꂽ�Ǘ���ʂ𑽂��̕��@�ŕύX�ł��܂��B���������̋@�\�ɂ͑㏞������܂�: �S�̂̍\���̋L�q���ǂ�Ŋw�Ԃɂ͒����̂ŁA���͂Ő���������A���̏͂����̖{�ł����Ƃ������Ȃ��Ă��܂��܂��B�ł��̂� symfony �� Web �T�C�g�͂��̍\�����w�Ԃ��߂̏����ɂȂ�ǉ����\�[�X��񎦂��܂�: Admin �W�F�l���[�^�[�̃`�[�g�V�[�g���}14-7�ōČ�����Ă܂��B[http://www.symfony-project.org/uploads/assets/sfAdminGeneratorRefCard.pdf](http://www.symfony-project.org/uploads/assets/sfAdminGeneratorRefCard.pdf)����ۑ����A���̏͂̂��̗��ǂނƂ��ɂ���𓪂̂Ȃ��ɂƂǂ߂Ă����Ă��������B

���̃Z�N�V�����̗�́A`BlogComment` �N���X�̒�`�Ɋ�Â��� `article` �Ǘ����W���[���Ɠ��l�� `comment` �Ǘ����W���[���𒲐����܂��B`propel:generate-admin` �^�X�N�����s���Č�҂��쐬���܂�:

    $ php symfony propel:generate-admin backend BlogComment --module=comment

�}14-4 - Admin �W�F�l���[�^�[�̃`�[�g�V�[�g

![Admin �W�F�l���[�^�[�̃`�[�g�V�[�g](http://www.symfony-project.org/images/book/1_4/F1404 " Admin �W�F�l���[�^�[�̃`�[�g�V�[�g")

### �t�B�[���h

�f�t�H���g�ł́A`list` �r���[�̃J������ `schema.yml` �Œ�`�����J�����ł��B`new` �� `edit` �r���[�̃t�B�[���h�̓��f���Ɋ֘A�Â����ꂽ�t�H�[���Œ�`���܂� (`BlogArticleForm`)�B`generator.yml` �ɂ���āA�ǂ̃t�B�[���h���\������A�ǂꂪ��\���ł��邩��I�сA�I�u�W�F�N�g���f���Œ��ڑΉ�������̂��Ȃ��Ă��Ǝ��t�B�[���h��ǉ��ł��܂��B

#### �t�B�[���h�̐ݒ�

Admin �W�F�l���[�^�[�� `schema.yml` �t�@�C���̃J�������Ƃ�1�̃t�B�[���h�����܂��B`fields` �L�[�̉��ŁA���ꂼ��̃t�B�[���h�̕\�����@��t�H�[�}�b�g���@�Ȃǂ��C���ł��܂��B���Ƃ��΁A���X�g14-5�Ŏ������t�B�[���h�̐ݒ�� `title` �t�B�[���h�p�̃J�X�^�����x���N���X�Ɠ��̓^�C�v�A������ `content` �t�B�[���h�p�̃��x���ƃc�[���`�b�v���`���܂��B���̃Z�N�V�����ł��ꂼ��̃p�����[�^�[�����삷����@���ڍׂɐ������܂��B

���X�g14-5 - �J�����ɑ΂��ăJ�X�^�����x����ݒ肷��

    [yml]
    config:
      fields:
        title:
          label: Article Title
          attributes: { class: foo }
        content: { label: Body, help: Fill in the article body }

���X�g14-6�̂悤�ɁA���ׂẴr���[�ɑ΂��邱�̃f�t�H���g�̒�`�ɉ����āA�C�ӂ̃r���[ (`list`�A`filter`�A`form`�A`new` �� `edit`) �ɑ΂���t�B�[���h�̐ݒ���I�[�o�[���C�h�ł��܂��B

���X�g14-6 - �r���[�P�ʂŃO���[�o���Ȑݒ�r���[���I�[�o�[���C�h����

    [yml]
    config:
      fields:
        title:     { label: Article Title }
        content:   { label: Body }

      list:
        fields:
          title:   { label: Title }

      form:
        fields:
          content: { label: Body of the article }

����͈�ʓI�Ȍ����ł�: `fields` �L�[�̉��̃��W���[���S�̂ɑ΂��Đݒ肳���ݒ荀�ڂ̓r���[�ŗL�̗̈�ŃI�[�o�[���C�h�ł��܂��B�I�[�o�[���C�h�̃��[���͂��̂Ƃ���ł�:

  * `new` �� `edit` �� `form` ���p���� `form` �� `fields` ���p�����܂�
  * `list` �� `fields` ���p�����܂�
  * `filter` �� `fields` ���p�����܂�

#### display �ݒ�Ƀt�B�[���h��ǉ�����

`fields` �Z�N�V�����Œ�`�����t�B�[���h�͂��ꂼ��̃r���[�ɑ΂��ĕ\���A�B���A���Ԃɕ��ׂ�ȂǁA���܂��܂ȕ��@�ŕ��ނł��܂��B`display` �L�[�͂��̖ړI�̂��߂Ɏg���܂��B���Ƃ��΁A`comment` ���W���[���̃t�B�[���h�����Ԃɕ��ׂ�ɂ́A���X�g14-7�̃R�[�h���g���܂��B

���X�g14-7 - �\���t�B�[���h��I������ (`modules/comment/config/generator.yml`)

    [yml]
    config:
      fields:
        article_id: { label: Article }
        created_at: { label: Published on }
        content:    { label: Body }

      list:
        display:    [id, blog_article_id, content]

      form:
        display:
          NONE:     [blog_article_id]
          Editable: [author, content, created_at]

�}14-5�̂悤�� `list` ��3�̃J������\�����A�}14-6�̂悤�ɁA`new` �� `edit` �t�H�[����2�̃O���[�v�ɏW�߂�ꂽ4�̃t�B�[���h��\�����܂��B

�}14-5 - `comment` ���W���[���� `list` �r���[�����̃J�X�^���J�����ݒ�

![comment ���W���[���� list �r���[�����̃J�X�^���J�����ݒ�](http://www.symfony-project.org/images/book/1_4/F1405.png "comment ���W���[���� list �r���[�����̃J�X�^���J�����ݒ�")

�}14-6 - `comment` ���W���[���� `edit` �r���[�����Ńt�B�[���h�𕪗ނ���

![comment ���W���[���� edit �r���[���Ńt�B�[���h�𕪗ނ���](http://www.symfony-project.org/images/book/1_4/F1406.png "comment ���W���[���� edit �r���[���Ńt�B�[���h�𕪗ނ���")

`display` �ݒ��2�̕��@�ŗ��p�ł��܂�:

  * `list` �r���[�ɑ΂���: �\������J�����ƕ\������鏇����I�Ԃ��߂ɒP���Ȕz��Ƀt�B�[���h��u���܂��B
  * `form`�A`new` �� `edit` �r���[�ɑ΂���: �O���[�v�̖��O���L�[�Ƃ���t�B�[���h���O���[�v��������̂ɘA�z�z��A�������͖��O�̂Ȃ��O���[�v�ɑ΂��� `NONE` ���g���܂��B�l�̓J�����̖��O�ŕ��בւ���ꂽ�z��̂܂܂ł��B�t�H�[���N���X�ɎQ�Ƃ���邷�ׂĂ̕K�{�t�B�[���h�̈ꗗ��\�����邱�Ƃɂ͒��ӂ𕥂��Ă��������B�����Ȃ��Ɨ\�����ʃo���f�[�V�����G���[�ɑ������邩������܂���(��10�͂��Q�Ƃ��Ă�������)�B

#### �J�X�^���t�B�[���h

���R�̂��ƂȂ���A`generator.yml` �Őݒ肳�ꂽ�t�B�[���h�̓X�L�[�}�Œ�`���ꂽ���ۂ̃J�����ɑΉ����Ă���K�v�͂���܂���B�֘A�N���X���J�X�^���Q�b�^�[��񋟂���ꍇ�A����� `list` �r���[�̂��߂̃t�B�[���h�Ƃ��Ďg�����Ƃ��ł��܂�; �Q�b�^�[����/�������̓Z�b�^�[�����݂���ꍇ�A���̃N���X�� `edit` �r���[�ł����p�ł��܂��B���Ƃ��΁A���X�g14-8�̂悤�ɁA`BlogArticle` ���f���� `getNbComments()` ���\�b�h�Ŋg���ł��܂��B

���X�g14-8 - ���f���ɃJ�X�^���Q�b�^�[��ǉ����� (`lib/model/BlogArticle.class.php`)

    [php]
    public function getNbComments()
    {
      return $this->countBlogComments();
    }

���X�g14-9�̂悤�ɁA`nb_comments` �͐������郂�W���[���Ńt�B�[���h�Ƃ��ė��p�ł��܂� (�Q�b�^�[�ł̓t�B�[���h���ɃL�������P�[�X���g���Ă��邱�Ƃɒ��ӂ��Ă�������)�B

���X�g14-9 - �J�X�^���Q�b�^�[�ŊǗ����W���[���p�̃J������񋟂��� (`backend/modules/article/config/generator.yml`)

    [yml]
    config:
      list:
        display:  [title, blog_author, blog_category, nb_comments]

`article` ���W���[���� `list` �r���[�͐}14-7�̂悤�ɂȂ�܂�

�}14-7 - `article` ���W���[���� `list` �r���[���̃J�X�^���t�B�[���h

![article ���W���[���� list �r���[�����̃J�X�^���t�B�[���h](http://www.symfony-project.org/images/book/1_4/F1407.png "article ���W���[���� list �r���[�����̃J�X�^���t�B�[���h")


#### �p�[�V�����t�B�[���h

���f���ɐݒu���ꂽ�R�[�h�̓v���[���e�[�V��������Ɨ����Ă��Ȃ���΂Ȃ�܂���B�O�o�� `getArticleLink()` ���\�b�h�̗�̓��C���[�����̌��������炵�Ă��܂���B�r���[�R�[�h�̂Ȃ��ɂ̓��f�����C���[�Ɍ������̂����邩��ł��B�܂��A�O�o�̃R�[�h�ł̓f�t�H���g�ł̓G�X�P�[�v���ꂽ `<a>` �^�O�Ƃ��ĕ\������Ă��܂��ł��傤�B���������@�ŁA�������ʂ���������ɂ́A�J�X�^���t�B�[���h�ɑΉ����� HTML ���o�͂���R�[�h�̓p�[�V�����e���v���[�g�őΉ�����ق����x�^�[�ł��B�K���AAdmin �W�F�l���[�^�[�ɂ���ăA���_�[�X�R�A�̃v���t�B�b�N�X�����t�B�[���h����錾�ł��܂��B���̏ꍇ�A���X�g14-11�� `generator.yml` �t�@�C���̓��X�g14-12�̂悤�ɏC������܂��B

���X�g14-12 - �p�[�V������ǉ��J�����Ƃ��Ďg���ɂ́A�v���t�B�b�N�X�� `_` ���w�肷��

    [yml]
    config:
      list:
        display: [id, _article_link, created_at]

������@�\������ɂ́A���X�g14-13�Ŏ������e�ŁA`modules/comment/tempaltes/` �f�B���N�g���� `_article_link.php` �p�[�V���������K�v������܂��B

���X�g14-13 - `list` �r���[�p�̃p�[�V�����e���v���[�g�̗� (`modules/comment/templates/_article_link.php`)

    [php]
    <?php echo link_to($BlogComment->getBlogArticle()->getTitle(), 'blog_article_edit', $BlogComment->getBlogArticle()) ?>

�p�[�V�����t�B�[���h�̃e���v���[�g�ł́A����̖��O�̕ϐ��Ō��݂̃I�u�W�F�N�g�ɃA�N�Z�X�ł���K�v������܂�(���̗�ł� `$BlogComment`)�B

Figure 14-8 - `article` ���W���[���� `list` �r���[���̃p�[�V�����t�B�[���h

![article���W���[����list�r���[���̃p�[�V�����t�B�[���h](http://www.symfony-project.org/images/book/1_4/F1408.png "article���W���[����list�r���[���̃p�[�V�����t�B�[���h")

���C���[�����̌��������炳��܂��B���̌����Ɋ��ꂽ��A�A�v���P�[�V�����̃����e�i���X���e�ՂɂȂ�܂��B

�p�[�V�����t�B�[���h�̃p�����[�^�[���J�X�^�}�C�Y����K�v������ꍇ�A`fields` �L�[�̉��Œʏ�̃t�B�[���h�Ɠ��������s���܂��B�A���_�[�X�R�A (`_`) ���L�[�̐擪�Ɋ܂߂Ȃ��ł��������B���X�g14-14���������������B

���X�g14-14 - �p�[�V�����t�B�[���h�̃v���p�e�B�� `fields` �L�[�̉��ŃJ�X�^�}�C�Y�ł���

    [yml]
    config:
      fields:
        article_link: { label: Article }

�p�[�V�����Ƀ��W�b�N�����݂���悤�ɂȂ�����A�R���|�[�l���g�ɒu�������邱�Ƃ��������߂��܂��B���X�g14-15�̂悤�ɁA�v���t�B�b�N�X�� `_` �� `~` �ɕύX���邱�ƂŁA�R���|�[�l���g�t�B�[���h���`�ł��܂��B

���X�g14-15 - �R���|�[�l���g��ǉ��J�����Ƃ��ė��p����B�v���t�B�b�N�X�� `~` ���g��

    [yml]
    config:
      list:
        display: [id, ~article_link, created_at]

���̂悤�ɂ���ƁA��������e���v���[�g�Ō��݂̃��W���[���� `articleLink` �R���|�[�l���g���Ăяo����܂��B

>**NOTE**
>�J�X�^���t�B�[���h�ƃp�[�V�����t�B�[���h�� `list`�A`new`�A`edit` �� `filter` �r���[�Ŏg�����Ƃ��ł��܂��B�����̃r���[�ɑ΂��ē����p�[�V�������g���ꍇ�A�R���e�L�X�g (`list`�A`new`�A`edit` �������� `filter`) �͕ϐ� `$type` �ɕۑ�����܂��B

### �r���[�̃J�X�^�}�C�Y

`new`�A`edit` �� `list` �r���[�̊O����ύX���邽�߂ɁA�e���v���[�g��ύX�������Ǝv�����Ƃ�����܂��B�����������͎����I�ɐ��������̂ŁA�������ꂽ�e���v���[�g��ύX����̂͂��܂�悢�A�C�f�A�ł͂���܂���B����� `generator.yml` �ݒ�t�@�C�����g���ׂ��ł��B���W���[�����𑹂Ȃ����ƂȂ��A�قƂ�ǂ��ׂĂ̕K�v�Ȃ��Ƃ��s���邩��ł��B

#### �r���[�̃^�C�g����ύX����

�t�B�[���h�̃J�X�^���Z�b�g�ɉ����āA`list`�A`new`�A`edit` �y�[�W�̓J�X�^���y�[�W�^�C�g���������܂��B���Ƃ��΁A`article` �r���[�̃^�C�g�����J�X�^�}�C�Y�������ꍇ�A���X�g14-16�̂悤�ɍs���܂��B`edit` �r���[�̌��ʂ͐}14-9�ɕ`����Ă��܂�

���X�g14-16 - ���ꂼ��̃r���[�ɑ΂��ăJ�X�^���^�C�g����ݒ肷�� (`backend/modules/article/config/generator.yml`)

    [yml]
    config:
      list:
        title: List of Articles

      new:
        title: New Article

      edit:
        title: Edit Article %%title%% (%%id%%)

�}14-9 - `article` ���W���[���� `edit` �r���[���̃J�X�^���^�C�g��

![article ���W���[���� edit �r���[���̃J�X�^���^�C�g��](http://www.symfony-project.org/images/book/1_4/F1409.png "article ���W���[���� edit �r���[���̃J�X�^���^�C�g��")

�f�t�H���g�̃^�C�g���̓N���X�̖��O���g���̂ŁA���f���������ȃN���X�̖��O���g���̂ł���΁A�����̃N���X���ŏ\���ł��邱�Ƃ͂悭����܂��B

>**TIP**
>`generator.yml` �̕�����̒l�ɂ����āA�t�B�[���h�̒l�� `%%` �ň͂܂ꂽ�t�B�[���h�̖��O��ʂ��ăA�N�Z�X�ł��܂��B

#### �c�[���`�b�v��ǉ�����

`list`�A`new`�A`edit` �� `filter` �r���[�����ɂ����āA�\�������t�B�[���h���L�q���邽�߂̏����ɂȂ�c�[���`�b�v��ǉ��ł��܂��B���Ƃ��΁A�c�[���`�b�v�� `comment` ���W���[���� `edit` �r���[�� `blog_article_id` �t�B�[���h�ɒǉ�����ɂ́A���X�g14-17�̂悤�ɁA`fields` �̒�`�� `help` �v���p�e�B��ǉ����܂��B���ʂ͐}14-10�Ɏ�����Ă��܂��B

���X�g14-17 - `edit` �r���[�Ńc�[���`�b�v��ݒ肷�� (`modules/comment/config/generator.yml`)

    [yml]
    config:
      edit:
        fields:
          blog_article_id: { help: The current comment relates to this article }

�}14-10 - `comment` ���W���[���� `edit` �r���[���̃c�[���`�b�v

![comment ���W���[���� edit �r���[���̃c�[���`�b�v](http://www.symfony-project.org/images/book/1_4/F1410.png "comment ���W���[���� edit �r���[���̃c�[���`�b�v")

`list` �r���[�ɂ����āA�c�[���`�b�v�̓J�����̃w�b�_�[�ɕ\������܂�; `new`�A`edit`�A`filter` �r���[�ɂ����Ă����� field �^�O�̉��Ō���܂��B

#### ���t�̏������C������

���X�g14-18�ł���{��������Ă���悤�ɁA`date_format` �I�v�V�������g�����Ƃœ����ɃJ�X�^�������œ��t��\���ł��܂��B

���X�g14-18 `list` �r���[�̂Ȃ��œ��t�̏����ݒ������

    [yml]
    config:
      list:
        fields:
          created_at: { label: Published, date_format: dd/MM }

���̃p�����[�^�[�͈ȑO�̏͂Ő������ꂽ `format_date()` �w���p�[�Ɠ����t�H�[�}�b�g�p�����[�^�[���󂯂Ƃ�܂��B

>**SIDEBAR**
>�Ǘ���ʂ̃e���v���[�g�͍��ۉ��̏������ł��Ă��܂�
>
>admin �Ő������ꂽ���W���[���̓C���^�[�t�F�C�X�̕����� (�f�t�H���g�̃A�N�V�����̖��O�A�y�[�W�����̃w���v���b�Z�[�W�A�E�E�E) �ƃJ�X�^�������� (�^�C�g���A�J�����̃��x���A�w���v���b�Z�[�W�A�G���[���b�Z�[�W�A�E�E�E) �ō\������܂��B
>
>�C���^�[�t�F�C�X�̕�����̑�����|��@�\��symfony�ɓ��ڂ���Ă��܂��B�������Ǝ��̂��̂�ǉ����邩 `sf_admin` �J�^���O (`apps/frontend/i18n/sf_admin.XX.xml`�A`XX` �͌����ISO�R�[�h) �p�� `i18n` �f�B���N�g���ŃJ�X�^��XLIFF�t�@�C�����쐬���邱�ƂŊ����̂��̂��I�[�o�[���C�h�ł��܂�
>
>�������ꂽ�e���v���[�g�Ō����邷�ׂẴJ�X�^��������������I�ɍ��ۉ�����܂� (���Ȃ킿�A`__()`�w���p�[�ւ̌Ăяo���ƈꏏ��)�B���̂��Ƃ͑O�̏͂Ő��������悤�ɁA`apps/frontend/i18n/` �f�B���N�g���� XLIFF �t�@�C���Ƀt���[�Y�̖|���ǉ����邱�ƂŁA�������ꂽ�Ǘ���ʂ��ȒP�ɖ|��ł��邱�Ƃ��Ӗ����܂��B
>
>`i18n_catalogue` �p�����[�^�[���w�肷�邱�ƂŃJ�X�^��������p�Ɏg����f�t�H���g�̃J�^���O��ύX�ł��܂�:
>
>     [yml]
>     generator:
>       class: sfPropelGenerator
>       param:
>         i18n_catalogue: admin

### list �r���[�ŗL�̃J�X�^�}�C�[�[�V����

`list` �r���[�́A�\�`���A�������͂��ׂĂ̏ڍׂȓ��e����s�ɐςݏd�˂�ꂽ��ԂŁA���R�[�h�̏ڍׂ�\���ł��܂��B����̓t�B���^�[�A�y�[�W�����ƃ\�[�g�@�\���܂݂܂��B�����̋@�\�͐ݒ�ɂ���ĕύX�ł��܂��B�ڍׂ͂��̃Z�N�V�����Ő������܂��B

#### ���C�A�E�g��ύX����

�f�t�H���g�ł́A`list` �r���[�� `edit` �r���[�Ԃ̃n�C�p�[�����N�͎�L�[�̃J�����ɂ���Đ�������܂��B�}14-8�ɖ߂�ƁA�R�����g���X�g�� `id` �J���������ꂼ��̃R�����g�̎�L�[��\�����邾���łȂ��A���[�U�[�� `edit` �r���[�ɃA�N�Z�X���邱�Ƃ�������n�C�p�[�����N��񋟂��܂��B

�ʂ̃J�����Ɍ���郌�R�[�h�̏ڍד��e�ւ̃n�C�p�[�����N���]�܂����̂ł���΁A`display` �L�[�̓��� (`=`) ���v���t�B�b�N�X�Ƃ��ăJ�����̖��O�ɒǉ����܂��B���X�g14-19�� `list` �R�����g�̕\���t�B�[���h���� `id` ���������đ���� `content` �t�B�[���h�Ƀn�C�p�[�����N��u�����@�������Ă��܂��B�}14-11�̃X�N���[���V���b�g���m�F���Ă��������B

���X�g14-19 - `edit` �r���[�̂��߂̃n�C�p�[�����N�� `list` �r���[�Ɉړ������� (`modules/comment/config/gererator.yml`)

    [yml]
    config:
      list:
        display: [_article_link, =content]

�}14-11 - `comment` ���W���[���� `list` �r���[�̂Ȃ��ŁA�����N��ʂ̃J������� `edit` �r���[�Ɉړ�������

![comment ���W���[���� list �r���[���ŁA�����N��ʂ̃J������� edit �r���[�Ɉړ�������](http://www.symfony-project.org/images/book/1_4/F1411.png "comment ���W���[���� list �r���[���ŁA�����N��ʂ̃J������� edit �r���[�Ɉړ�������")

�f�t�H���g�ł́A�ȑO�����ꂽ�悤�ɁA`list` �r���[�̓t�B�[���h���J�����Ƃ��ĕ\�������`tabular`���C�A�E�g���g���܂��B������ `stacked` ���C�A�E�g���g���ăt�B�[���h���e�[�u���̑S�����ڂ����L�q����P�Ƃ̕�����ɘA�����邱�Ƃ��ł��܂��B`stacked` ���C�A�E�g��I�ԏꍇ�A`params` �L�[�Ƀ��X�g�̂��ꂼ��̍s�̒l���`����p�^�[����g�ݍ��܂Ȃ���΂Ȃ�܂���B���Ƃ��΁A���X�g14-20�� `comment` ���W���[���� `list` �r���[�ɑ΂��� `stacked` ���C���[���`���܂��B���ʂ͐}14-12�ł��B

���X�g14-20 - `list` �r���[�� `stacked` ���C�A�E�g���g�� (`modules/comment/cofig/generator.yml`)

    [yml]
    config:
      list:
        layout:  stacked
        params:  |
          %%=content%%<br />
          (sent by %%author%% on %%created_at%% about %%_article_link%%)
        display:  [created_at, author, content]

�}14-12 - `comment` ���W���[���� `list` �r���[���̃X�^�b�N���C�A�E�g

![comment ���W���[���� list �r���[���̃X�^�b�N���C�A�E�g](http://www.symfony-project.org/images/book/1_4/F1412.png "comment ���W���[���� list �r���[���̃X�^�b�N���C�A�E�g")

`tabular` ���C�A�E�g�� `display` �L�[�̉��Ńt�B�[���h�̔z���K�v�Ƃ��܂����A`stacked` ���C�A�E�g�͂��ꂼ��̃��R�[�h�ɑ΂��Đ������ꂽ HTML �R�[�h�̂��߂� `params` �L�[���g�����Ƃɗ��ӂ��Ă��������B�������Ȃ���A�C���^���N�e�B�u�ȃ\�[�g�ɑ΂��ė��p�ł���J�����w�b�_�[�����肷�邽�߂� `display` �z�� `stacked` ���C�A�E�g�ł��g���܂�

#### ���ʂ��t�B���^�����O����

`list` �r���[�ɂ����āA�t�B���^�[�̃C���^���N�V�����̃Z�b�g��ǉ��ł��܂��B�����̃t�B���^�[�ɂ���āA���[�U�[�͌��ʂ���菭�Ȃ��\�����đ����]�ނ��̂ɓ��B�ł��܂��B�t�B�[���h���̔z��ŁA`filter` �L�[�̉��Ƀt�B���^�[��ݒ肵�܂��B���Ƃ��΁A�}14-13�̃t�B���^�[�{�b�N�X�Ɠ����悤�Ȃ��̂�\������ɂ́A���X�g14-21�̂悤�ɁA`blog_article_id`�A`author` �t�B�[���h�� `created_at` �t�B�[���h��̃t�B���^�[���R�����g��`list` �r���[�ɒǉ����܂��B

���X�g14-21 - `list` �r���[�Ńt�B���^�[��ݒ肷�� (`modules/comment/config/generator.yml`)

    [yml]
    config:
      list:
        layout:  stacked
        params:  |
          %%=content%% <br />
          (sent by %%author%% on %%created_at%% about %%_article_link%%)
        display:  [created_at, author, content]

      filter:
        display: [blog_article_id, author, created_at]

�}14-13 - `comment` ���W���[���� `list` �r���[���̃t�B���^�[

![comment ���W���[���� list �r���[���̃t�B���^�[](http://www.symfony-project.org/images/book/1_4/F1413.png "comment ���W���[���� list �r���[���̃t�B���^�[")

symfony �ɕ\�������t�B���^�[�̓X�L�[�}�Œ�`�����J�����̌^�Ɉˑ����A�t�B���^�[�t�H�[���N���X�ŃJ�X�^�}�C�Y�ł��܂�:

  * �e�L�X�g�J���� (���Ƃ��� `comment` ���W���[������ `author` �t�B�[���h) �ɑ΂��āA�t�B���^�[�̓e�L�X�g�x�[�X�̌������\�ɂ���e�L�X�g���͂ł� (���C���h�J�[�h�������I�ɒǉ�).
  * �O���L�[ (���Ƃ��� `comment` ���W���[�������� `blog_article_id` �t�B�[���h�̃��X�g) �ɑ΂��āA�t�B���^�[�͊֘A����e�[�u���̃��R�[�h�̃h���b�v�_�E�����X�g�ł��B�f�t�H���g�ł́A�h���b�v�_�E�����X�g�̃I�v�V�����͊֘A����N���X�� `__toString()` ���\�b�h�ɂ���ĕԂ������̂ł��B
  * ���t�̃J���� (���Ƃ��� `comment` �J�������� `created_at`�t�B�[���h) �ɑ΂��āA�t�B���^�[�̓��b�`�ȓ��t�^�O�̃y�A�ŁA���Ԃ̊Ԋu��I���ł���悤�ɂ��܂��B
  * �u�[���^�̃J�����ɑ΂��āA�t�B���^�[�� `true` �� `false` �� `true or false` �I�v�V���������h���b�v�_�E�����X�g�ł��B�Ō�̒l�̓t�B���^�[���ď��������܂��B

`new` �� `edit` �r���[���t�H�[���N���X�Ɍ��т����Ă���悤�ɁA���f���Ɋ֘A����f�t�H���g�̃t�B���^�[�t�H�[���N���X�ł� (���Ƃ��� `BlogArticle` ���f���ɑ΂��� `BlogArticleFormFilter`)�B�t�B���^�[�t�H�[���ɑ΂��ăJ�X�^���N���X���`���邱�ƂŁA�t�H�[���t���[�����[�N�̗͂����p�����ׂĂ̗��p�\�ȃt�B���^�[�E�B�W�F�b�g���g�����ƂŃt�B���^�[�t�B�[���h���J�X�^�}�C�Y�ł��܂��B���X�g14-22�Ŏ������悤�ɁA`filter` �G���g���[�̉��� `class` ���`���邱�ƂŊȒP�Ɏ����ł��܂��B

���X�g14-22 - �t�B���^�����O�Ɏg����t�H�[���N���X���J�X�^�}�C�Y����

    [yml]
    config:
      filter:
        class: BackendArticleFormFilter

>**TIP**
>�t�B���^�[���ꏏ�ɖ����ɂ���ɂ́A�t�B���^�[�p�� `class` �� `false` ���w�肷�邾���ł��B

�t�B���^�[���C�����邽�߂Ƀp�[�V�����t�B���^�[���g�����Ƃ��ł��܂��B���ꂼ��̃p�[�V�����̓t�H�[���������_�����O���邳���� `form` �� HTML�� `attributes` ���󂯂Ƃ�܂��B���X�g14-23�̓p�[�V�����ȊO�̃f�t�H���g�̂ӂ�܂���͕킷������̗�������Ă��܂��B

���X�g14-23 - �p�[�V�����t�B���^�[���g��

    [php]
    // templates/_state.php �ŁA�p�[�V�������`����
    <?php echo $form[$name]->render($attributes->getRawValue()) ?>

    // config/generator.yml �Ńp�[�V�����t�B���^�[�����X�g�ɒǉ�����
    config:
      filter: [created_at, _state]

#### ���X�g���\�[�g����

`list` �r���[�ɂ����āA�}14-18�Ŏ������悤�ɁA�e�[�u���̃w�b�_�[�̓��X�g���Ăя��Ԃɕ��ׂ邽�߂Ɏg����n�C�p�[�����N�ł��B�����̃w�b�_�[�� `tabular` ���C�A�E�g�� `stacked` ���C�A�E�g�̗����ŕ\������܂��B�����̃����N���N���b�N����ƃ��X�g�̏��Ԃ��Ĕz�u���� `sort` �p�����[�^�[�Ńy�[�W�������[�h����܂��B

�}14-14 - `list` �r���[�̃e�[�u���w�b�_�[�̓\�[�g���R���g���[������

![list �r���[�̃e�[�u���w�b�_�[�̓\�[�g�̓R���g���[������](http://www.symfony-project.org/images/book/1_4/F1414.png "list �r���[�̃e�[�u���w�b�_�[�̓\�[�g���R���g���[������")

����ЂƂ̃J�����ɂ���ă\�[�g���ꂽ���X�g�𒼐ڎw�肷��\�����ė��p�ł��܂�:

    [php]
    <?php echo link_to('���t���Ƃ̃R�����g�̃��X�g', '@blog_comment?sort=created_at&sort_type=desc' ) ?>

`generator.yml` �t�@�C�������� `list` �r���[�ɑ΂��Ē��ڃf�t�H���g�� `sort` �̏��Ԃ��`���邱�Ƃ��\�ł��B�\���̓��X�g14-24�Ŏ����ꂽ��ɏ]���܂��B

���X�g14-24 - `list` �r���[�̂Ȃ��Ńf�t�H���g�� `sort` �t�B�[���h��ݒ肷��

    [yml]
    config:
      list:
        sort:   created_at
        # �\�[�g�̏������w�肷�邽�߂́A��֍\��
        sort:   [created_at, desc]

>**NOTE**
>���ۂ̃J�����ɑΉ�����t�B�[���h�������A�\�[�g�̃R���g���[���@�\�ɕϊ�����܂��B�J�X�^���������̓p�[�V�����t�B�[���h�ɂ͑Ή����Ă��܂���B

#### �p�W�l�[�V�������J�X�^�}�C�Y����

�������ꂽ�Ǘ���ʂ͑傫�ȃe�[�u�������������I�ɏ������܂��B`list` �r���[���f�t�H���g�Ńp�W�l�[�V�������g������ł��B�e�[�u�����̎��ۂ̍s�̐����y�[�W���Ƃ̍s�̍ő吔���z����ꍇ�A�p�W�l�[�V�����̃R���g���[���@�\�����X�g�����ɕ\������܂��B���Ƃ��΁A�}14-15�̓e�[�u���� 6 ���̃e�X�g�R�����g�����郊�X�g�ŁA1 �y�[�W�ɕ\������̂� 5 ���ɐ�������Ă��܂��B�p�W�l�[�V�����ɂ��A�\�������s�݂̂��f�[�^�x�[�X��������I�ɒ��o�����̂Ńp�t�H�[�}���X���ۏ؂���A�Ǘ����W���[���ɂ���ĉ��S���s������e�[�u�����Ǘ��ł���̂Ń��[�U�[�r���e�B���ۏ؂���܂��B

�}14-15 - �������X�g�Ńp�W�l�[�V�����̃R���g���[���@�\���\�������

![�������X�g�Ńp�W�l�[�V�����̃R���g���[���@�\���\�������](http://www.symfony-project.org/images/book/1_4/F1415.png "�������X�g�Ńp�W�l�[�V�����̃R���g���[���@�\���\�������")

`max_per_page` �p�����[�^�[�ɂ���Ă��ꂼ��̃y�[�W�ɕ\������郌�R�[�h�̐����J�X�^�}�C�Y�ł��܂�:

    [yml]
    config:
      list:
        max_per_page:   5

#### �y�[�W�̕\�������������邽�߂� Join ���g��

�f�t�H���g�ł́AAdmin �W�F�l���[�^�[��`doSelect()` ���g���ă��R�[�h�̃��X�g���擾���܂��B�������A���X�g�Ŋ֘A�I�u�W�F�N�g���g���ꍇ�A���X�g��\�����邽�߂ɕK�v�ȃf�[�^�x�[�X�N�G���̐����}�ɑ����邱�Ƃ�����܂��B���Ƃ��΁A�R�����g�̃��X�g�ŋL���̖��O��\���������ꍇ�A�֘A���� `BlogArticle` �I�u�W�F�N�g���������邽�߂Ƀ��X�g���̂��ꂼ��̓��e�ɑ΂���ǉ��N�G�����K�v�ł��B�ł��̂ŁA�N�G���̐����œK�����邽�߂ɁA`doSelectJoinXXX()` ���\�b�h���g���y�[�W���[�������������ꍇ�����邩������܂���B����� `peer_method` �p�����[�^�[�Ŏw��ł��܂��B

    [yml]
    config:
      list:
        peer_method: doSelectJoinBlogArticle

18�͂ł� Join �̊T�O�ɂ��Ă��L�͈͂ɐ������܂��B

### new �� edit �r���[�ŗL�̃J�X�^�}�C�Y

`new` �������� `edit` �r���[�ɂ����āA���[�U�[�͐V�������R�[�h�������͓n���ꂽ���R�[�h�ɑ΂��Ă��ꂼ��̃J�����̒l���C���ł��܂��B�f�t�H���g�ł́Aadmin �W�F�l���[�^�[�Ŏg����t�H�[���̓��f��: `BlogArticle` ���f���ɑ΂��� `BlogArticleForm` �Ɋ֘A����t�H�[���ł��B���X�g14-25�Ŏ������悤�� `form` �G���g���[�̉��� `class` ���`���邱�ƂŎg���N���X���J�X�^�}�C�Y�ł��܂��B

���X�g14-25 - `new` �� `edit` �r���[�Ɏg����t�H�[���N���X���J�X�^�}�C�Y����

    [yml]
    config:
      form:
        class: BackendBlogArticleForm

�J�X�^���t�H�[���N���X�𗘗p���邱�Ƃ� admin �W�F�l���[�^�[�p�̃E�B�W�F�b�g�ƃo���f�[�^�[���ׂĂ��J�X�^�}�C�Y�ł��܂��Bfrontend �A�v���P�[�V�����ɑ΂��ăf�t�H���g�̃t�H�[���N���X���g�����ʂɃJ�X�^�}�C�Y����܂��B

���X�g14-26�Ŏ������悤�� `generator.yml` �ݒ�t�@�C���Ń��x���A�w���v���b�Z�[�W�A�ƃt�H�[���̃��C�A�E�g�𒼐ڃJ�X�^�}�C�Y���邱�Ƃ��ł��܂��B

���X�g14-26 - �t�H�[���\�����J�X�^�}�C�Y����

    [yml]
    config:
      form:
        display:
          NONE:     [article_id]
          Editable: [author, content, created_at]
        fields:
          content:  { label: body, help: "The content can be in the Markdown format" }

#### �p�[�V�����t�B�[���h������

�p�[�V�����t�B�[���h�� `list` �r���[�̂悤�� `new` �� `edit` �r���[�ň����܂��B

### �O���L�[������

�X�L�[�}���e�[�u���̃����[�V�������`����ꍇ�A�������ꂽ Admin ���W���[���͂�������p���āA��莩�������ꂽ�R���g���[�����@��񋟂���̂ŁA�����[�V�����̊Ǘ���Ƃ��傢�Ɋȗ�������܂��B

#### ��Α��̃����[�V����

1�Α��̃e�[�u���̃����[�V������ Admin �W�F�l���[�^�[�ɂ���čl������܂��B�ȑO�̐}14-1�ŋL�q���ꂽ�悤�ɁA`blog_comment` �e�[�u���� `blog_article_id` �t�B�[���h��ʂ��� `blog_article` �e�[�u���Ƃ̊֌W�������܂��B`BlogComment` �N���X�̃��W���[���� Admin �W�F�l���[�^�[�ɂ���ď���������ꍇ�A`edit` �r���[�� `blog_article` �e�[�u�����̗��p�\�ȃ��R�[�h�� ID ������ `blog_article_id` ���h���b�v�_�E�����X�g�Ƃ��ĕ\�����܂� (�����}�͐}14-9���ēx�m�F)�B

`article` ���W���[��(���Έ�̃����[�V����)���̋L���Ɋ֘A����R�����g�̃��X�g��\������ꍇ�����l�ł��B

#### ���Α��̃����[�V����

symfony �͐}14-16�Ŏ������悤�ɑ��Α��̃����[�V�������l�����܂��B

�}14-16 - ���Α��̃����[�V����

![���Α��̃����[�V����](http://www.symfony-project.org/images/book/1_4/F1416.png "���Α��̃����[�V����")

�����[�V�����������_�����O���邽�߂Ɏg����E�B�W�F�b�g���J�X�^�}�C�Y���邱�ƂŁA�t�B�[���h�̃����_�����O�𒲐��ł��܂�(�}14-17�Ő���):

�}14-17 - ���Α��̃����[�V�����ɑ΂��ė��p�ł���R���g���[���@�\

![���Α��̃����[�V�����ɑ΂��ė��p�ł���R���g���[���@�\](http://www.symfony-project.org/images/book/1_4/F1417.png "���Α��̃����[�V�����ɑ΂��ė��p�ł���R���g���[���@�\")

### �C���^���N�V������ǉ�����

Admin ���W���[���̓��[�U�[���ʏ��CRUD�I�y���[�V���������s�ł���悤�ɂ��܂����A�r���[�ɑ΂��ēƎ��̃C���^���N�V������ǉ�����������͉\�ȃC���^���N�V�����𐧌����邱�Ƃ��ł��܂��B���Ƃ��΁A���X�g14-27�Ŏ�����Ă���C���^���N�V�������`���邱�Ƃ� `article` ���W���[����̂��ׂĂ� CRUD �A�N�V�����Ƀf�t�H���g�ŃA�N�Z�X�ł���悤�ɂȂ�܂��B

���X�g14-27 - ���ꂼ��̃r���[�ɑ΂��ăC���^���N�V�������`���� (`backend/modules/article/config/generator.yml`)

    [yml]
    config:
      list:
        title:          List of Articles
        object_actions:
          _edit:         ~
          _delete:       ~
        batch_actions:
          _delete:       ~
        actions:
          _new:          ~

      edit:
        title:          Body of article %%title%%
        actions:
          _delete:       ~
          _list:         ~
          _save:         ~
          _save_and_add: ~

`list` �r���[�ɂ����āA�A�N�V�����̐ݒ肪3���݂��܂�: ���ׂẴI�u�W�F�N�g�ɑ΂��ė��p�\�ȃA�N�V���� (`object_actions`)�A�I�u�W�F�N�g�̑I���ɑ΂��ė��p�\�ȃA�N�V���� (`batch_actions`)�A�y�[�W�S�̂ɑ΂��ė��p�\�ȃA�N�V���� (`actions`) �ł��B���X�g14-27�Œ�`���ꂽ���X�g�̃C���^���N�V�����͐}14-18�̂悤�Ƀ����_�����O���܂��B���ꂼ��̍s�̓��R�[�h��ҏW���邽�߂̃{�^���ƃ��R�[�h���폜���邽�߂̃{�^���A�����ɉ����āA���R�[�h�̑I�����폜���邽�߂ɂ��ꂼ��̍s�̏��1�̃`�F�b�N�{�b�N�X��\�����܂��B���X�g�̈�ԉ��ŁA1�̃{�^���ɂ���ĐV�������R�[�h����邱�Ƃ��ł��܂��B

�}14-18 - `list` �r���[���̃C���^���N�V����

![list �r���[���̃C���^���N�V����](http://www.symfony-project.org/images/book/1_4/F1418.png "list �r���[���̃C���^���N�V����")

`new` �� `edit` �r���[�ɂ����āA��x�ɕҏW����郌�R�[�h��1�����ł���A(`actions` �̂��Ƃ�) ��`����A�N�V�����̃Z�b�g��1�����ł��B���X�g14-27�Œ�`���ꂽ `edit` �C���^���N�V�����͐}14-23�̂悤�Ƀ����_�����O����܂��B`save` �A�N�V������ `save_and_add` �A�N�V�����͌��݂̕ҏW�����R�[�h�ɕۑ����܂��B�����̃A�N�V�����̈Ⴂ�́A`save` �A�N�V�����͕ۑ��������ƂŌ��݂̃��R�[�h��� `edit` �r���[��\������̂ɑ΂��āA`save_adn_add` �A�N�V�����͕ʂ̃��R�[�h��ǉ����邽�߂� `new` �r���[��\�����邱�Ƃł��B`save_and_add` �A�N�V�����͑������܂ɑ����̃��R�[�h��ǉ�����Ƃ��ɔ��ɕ֗��ȃV���[�g�J�b�g�ł��B`delete` �A�N�V�����̈ʒu�Ɋւ��ẮA����͂ق��̃{�^�����番������Ă���̂ŁA���[�U�[������ăN���b�N���邱�Ƃ͂���܂���B

�A���_�[�X�R�A (`_`) �Ŏn�܂�C���^���N�V�������� symfony �ɑ΂��Ă����̃A�N�V�����ɑΉ�����f�t�H���g�̃A�C�R���ƃA�N�V�������g���悤�ɓ`���܂��BAdmin �W�F�l���[�^�[�� `_edit`�A`_delete`�A`_new`�A`_list`�A`_save`�A`_save_and_add` �� `_create` �𗝉����܂��B

�}14-19 - `edit` �r���[���̃C���^���N�V����

![edit �r���[���̃C���^���N�V����](http://www.symfony-project.org/images/book/1_4/F1419.png "edit �r���[���̃C���^���N�V����")

�������J�X�^���C���^���N�V������ǉ����邱�Ƃ��ł��܂��B���̏ꍇ���X�g14-28�Ŏ������悤�ɁA�A���_�[�X�R�A�Ŏn�܂�Ȃ����O�A�ƌ��݂̃��W���[���̂Ȃ��̃^�[�Q�b�g�̃A�N�V�������w�肵�Ȃ���΂Ȃ�܂���B

���X�g14-28 - �J�X�^���C���^���N�V�������`����

    [yml]
    list:
      title:          List of Articles
      object_actions:
        _edit:        -
        _delete:      -
        addcomment:   { label: Add a comment, action: addComment }

�}14-20�Ŏ������悤�ɁA���X�g�ɂ����邻�ꂼ��̃A�N�V������ `Add a comment` �����N��\�����܂��B������N���b�N���邱�ƂŌ��݂̃��W���[������ `addComment` �A�N�V�������Ăяo�����Ƃ��s���܂��B���݂̃I�u�W�F�N�g�̎�L�[�̓��N�G�X�g�p�����[�^�[�Ɏ����I�ɒǉ�����܂��B

�}14-20 - `list` �r���[�����̃J�X�^���C���^���N�V����

![list �r���[���̃J�X�^���C���^���N�V����](http://www.symfony-project.org/images/book/1_4/F1420.png "list�r���[���̃J�X�^���C���^���N�V����")

`addComment` �A�N�V�����̓��X�g14-29�̂悤�Ɏ����ł��܂��B

���X�g14-29 - �J�X�^���C���^���N�V�����A�N�V���� (`actions/actions.class.php`)

    [php]
    public function executeAddComment($request)
    {
      $comment = new BlogComment();
      $comment->setArticleId($request->getParameter('id'));
      $comment->save();

      $this->redirect('blog_comment_edit', $comment);
    }

�o�b�`�X�N���v�g�� `ids` ���N�G�X�g�p�����[�^�[�̂Ȃ��őI�����ꂽ���R�[�h�̎�L�[�̔z����󂯂Ƃ�܂��B

�A�N�V�����ɂ��čŌ�̈ꌾ�ł�: ����J�e�S���̂��߂ɃA�N�V���������S�ɗ}���������ꍇ�A���X�g14-30�Ŏ������悤�ɁA��̃��X�g���g���܂��B

���X�g14-30 - `list` �r���[�̂��ׂẴA�N�V��������������

    [yml]
    config:
      list:
        title:   List of Articles
        actions: {}

### �t�H�[���̃o���f�[�V����

�o���f�[�V������ `new` �� `edit` �r���[�Ŏg����t�H�[���������I�ɍl�����܂��B�Ή�����t�H�[���N���X��ҏW���邱�Ƃł��̃t�H�[�����J�X�^�}�C�Y�ł��܂��B

### �N���f���V�����𗘗p���ă��[�U�[�̃A�N�V�����𐧌�����

����� Admin ���W���[���ɑ΂��āA���p�\�ȃt�B�[���h�ƃC���^���N�V�����̓��O�C�����[�U�[�̃N���f���V�����ɂ���ĕω����܂� (symfony �̃Z�L�����e�B�@�\�̐����Ɋւ��Ă�6�͂��Q��)�B

�K�؂ȃN���f���V�����������[�U�[�݂̂ɑ΂��ĕ\�������悤�ɂ��邽�߂ɃW�F�l���[�^�[�����̃t�B�[���h�� `credentials` �p�����[�^�[���l���ɓ���܂��B����� `list`�G���g���[�ɑ΂��ċ@�\���܂��B�����āA�W�F�l���[�^�[�̓N���f���V�����ɂ��������ăC���^���N�V�������B�����Ƃ��ł��܂��B���X�g14-31�͂����̋@�\�̂���{�������Ă��܂��B

���X�g14-31 - �N���f���V�������g�� (`generator.yml`)

    [yml]
    config:
      # admin�N���f���V�����������[�U�[�ɑ΂��Ă̂�id�J�����͕\�������
      list:
        title:          List of Articles
        display:        [id, =title, content, nb_comments]
        fields:
          id:           { credentials: [admin] }

      # addcomment�C���^���N�V������admin�N���f���V�����������[�U�[�ɐ��������
      actions:
        addcomment: { credentials: [admin] }

�������W���[���̃v���[���e�[�V�������C������
-----------------------------------------------

�Ǝ��̃X�^�C���V�[�g��K�p���邾���łȂ��A�f�t�H���g�̃e���v���[�g�ŏ㏑�����邱�ƂŁA�������ꂽ���W���[���̃v���[���e�[�V�����������̃O���t�B�J���ȕ\�Ƀ}�b�`����悤�ɁA���̃��W���[�����C���ł��܂��B

### �J�X�^���X�^�C���V�[�g���g��

�������ꂽ HTML �R�[�h�͍\�������ꂽ���e�����̂ŁA�v���[���e�[�V�����ł��Ȃ����]�ނ��Ƃ�傢�ɍs�����Ƃ��ł��܂��B

���X�g14-32�Ŏ������悤�ɁA`css` �p�����[�^�[�𐶐����ꂽ�W�F�l���[�^�[�̐ݒ�ɒǉ����邱�ƂŁAAdmin ���W���[���ɑ΂��āA�f�t�H���g�̑���ɃJ�X�^�� CSS ���`�ł��܂��B

���X�g14-32 - �f�t�H���g�̑���ɃJ�X�^���X�^�C���V�[�g���g��

    [yml]
    generator:
      class: sfPropelGenerator
      param:
        model_class:           BlogArticle
        theme:                 admin
        non_verbose_templates: true
        with_show:             false
        singular:              BlogArticle
        plural:                BlogArticles
        route_prefix:          blog_article
        with_propel_route:     1
        actions_base_class:    sfActions
        css:                   mystylesheet

������̕��@�Ƃ��āA�r���[�P�ʂŃX�^�C�����㏑�����邽�߂Ƀ��W���[���� `view.yml` �ɂ���Ē񋟂���郁�J�j�Y�������p�ł��܂��B

### �J�X�^���w�b�_�[�ƃt�b�^�[�𐶐�����

`list`�A`new`�A`edit` �r���[�̓w�b�_�[�ƃt�b�^�[�����e���v���[�g���n���I�Ɋ܂ނ��Ƃ��ł��܂��BAdmin ���W���[���� `templates/` �f�B���N�g���̂Ȃ��ɂ͂��̂悤�ȕ����e���v���[�g�͑��݂��܂��񂪁A�����e���v���[�g�������I�ɃC���N���[�h����ɂ͈ȉ��̖��O��1��ǉ�����K�v������܂�:

    _list_header.php
    _list_footer.php
    _form_header.php
    _form_footer.php

���Ƃ��΁A�J�X�^���w�b�_�[�� `article/edit` �r���[�ɒǉ��������ꍇ�A���X�g14-33�̂悤�� `_form_header.php` �Ƃ������O�̃t�@�C�������܂��B����͒ǉ��̐ݒ�Ȃ��œ��삵�܂��B

���X�g14-33 - `edit` �w�b�_�[�p�[�V�����̗� (`modules/article/templates/_form_header.php`)

    [php]
    <?php if ($blog_article->getNbComments() > 0): ?>
      <h2>���̋L���ɂ�<?php echo $blog_article->getNbComments() ?>���̃R�����g������܂�</h2>
    <?php endif; ?>

`edit` �����e���v���[�g�̓N���X�ɂ���Ė������ꂽ�ϐ���ʂ��Ă��ł����݂̃I�u�W�F�N�g�ɃA�N�Z�X�\�ŁA`list` �����e���v���[�g�� `$pager` �ϐ���ʂ��Ă��ł����݂̃y�[�W���[�ɃA�N�Z�X�ł��邱�Ƃɗ��ӂ��Ă��������B


### �e�[�}���J�X�^�}�C�Y����

�J�X�^���v���𖞂������߂ɁA���W���[���� `templates/` �t�H���_�[�̂Ȃ��ŃI�[�o�[���C�h�\�Ńt���[�����[�N����p�����ꂽ�ʂ̕����e���v���[�g�����݂��܂��B

�W�F�l���[�^�[�̃e���v���[�g�͌ʂɏ㏑���ł��鏬���ȕ����ɕ����\�ŁA�A�N�V�����͈���ύX�ł��܂��B

�������Ȃ���A�������@�ł������̃��W���[���ɑ΂��Ă������㏑���������̂ł���΁A�����炭�͍ė��p�\�ȃe�[�}�����ׂ��ł��B�e�[�} (theme) �̓e���v���[�g�ƃA�N�V�����̃T�u�Z�b�g�ŁA`generator.yml` �̎n�߂Ńe�[�}�̒l�Ɏw�肳�ꂽ�ꍇ�AAdmin ���W���[���̂Ȃ��Ŏg���܂��B�f�t�H���g�̃e�[�}�ƈꏏ�ɁAsymfony �� `$sf_symfony_lib_dir/plugins/sfPropelPlugin/data/generator/sfPropelModule/admin/` �Œ�`���ꂽ�t�@�C�����g���܂��B

�e�[�}�̃t�@�C���� `data/generator/sfPropelModule/[theme_name]/` �f�B���N�g�������́A�v���W�F�N�g�̃c���[�\���ɐݒu���Ȃ���΂Ȃ炸�A�f�t�H���g�̃e�[�}����I�[�o�[���C�h�������t�@�C�����R�s�[���邱�ƂŐV�����e�[�}���g���n�߂邱�Ƃ��ł��܂� (`$sf_symfony_lib_dir/plugins/sfPropelPlugin/data/generator/sfPropelModule/admin/` �f�B���N�g���ɐݒu����܂�):

    // [theme_name]/template/templates/ �̃p�[�V����
    _assets.php
    _filters.php
    _filters_field.php
    _flashes.php
    _form.php
    _form_actions.php
    _form_field.php
    _form_fieldset.php
    _form_footer.php
    _form_header.php
    _list.php
    _list_actions.php
    _list_batch_actions.php
    _list_field_boolean.php
    _list_footer.php
    _list_header.php
    _list_td_actions.php
    _list_td_batch_actions.php
    _list_td_stacked.php
    _list_td_tabular.php
    _list_th_stacked.php
    _list_th_tabular.php
    _pagination.php
    editSuccess.php
    indexSuccess.php
    newSuccess.php

    // [theme_name]/parts �̃A�N�V����
    actionsConfiguration.php
    batchAction.php
    configuration.php
    createAction.php
    deleteAction.php
    editAction.php
    fieldsConfiguration.php
    filterAction.php
    filtersAction.php
    filtersConfiguration.php
    indexAction.php
    newAction.php
    paginationAction.php
    paginationConfiguration.php
    processFormAction.php
    sortingAction.php
    sortingConfiguration.php
    updateAction.php

�e���v���[�g�t�@�C���͎��ۂɂ̓e���v���[�g�̃e���v���[�g (templates of templates) �ł��邱�Ƃɒ��ӂ��Ă��������B���Ȃ킿�APHP �t�@�C���̓W�F�l���[�^�[�̐ݒ�Ɋ�Â��e���v���[�g�𐶐�������ʂȃ��[�e�B���e�B�ɂ���ĉ�͂���܂� (����̓R���p�C���[�V�����t�F�[�Y (compilation phase) �ƌĂ΂�܂�)�B�����e���v���[�g�����ۂɃu���E�W���O���Ă���ԂɎ��s�����PHP�R�[�h���܂܂Ȃ���΂Ȃ�Ȃ��̂ŁA�e���v���[�g�̃e���v���[�g�͍ŏ��̃p�X�̊Ԃ� PHP �R�[�h�����s���Ȃ��悤�ɂ��邽�߂ɑ�֍\�����g���܂��B���X�g14-34�̓f�t�H���g�̃e���v���[�g�̃e���v���[�g�̔����ł��B

���X�g14-34 - �e���v���[�g�̃e���v���[�g�̍\��

    [php]
    <h1>[?php echo <?php echo $this->getI18NString('edit.title') ?> ?]</h1>

    [?php include_partial('<?php echo $this->getModuleName() ?>/flashes') ?]

���̃��X�g�ɂ����āA(�R���p�C������) `<?` �ɂ���ē������ꂽPHP�R�[�h�͑����Ɏ��s����A`[?`�ɂ���ē������ꂽ���͎̂��s���݂̂Ɏ��s����܂����A�e���v���[�g�G���W���͍Ō�ɂ� `[?` �^�O�� `<?` �^�O�ɕϊ�����̂Ńe���v���[�g�̌��ʂ͂��̂悤�ɂȂ�܂�:

    [php]
    <h1><?php echo __('List of all Articles') ?></h1>

    <?php include_partial('article/flashes') ?>

�e���v���[�g�̃e���v���[�g�͈����ɂ����̂ŁA�Ǝ��̃e�[�}����肽���ꍇ�A�����Ƃ������߂��邱�Ƃ� `admin` �e�[�}����n�߁A�������C�����A���܂߂Ƀe�X�g���邱�Ƃł��B

>**TIP**
>�W�F�l���[�^�[�̃e�[�}���v���O�C���̃p�b�P�[�W�ɂ��邱�Ƃ��ł���̂ŁA�ė��p���������Ȃ�A�����̃A�v���P�[�V�����ɂ܂������ăf�v���C���邱�Ƃ��ȒP�ɂȂ�܂��B�ڍׂȏ���17�͂��Q�Ƃ��Ă��������B

-

>**SIDEBAR**
>�Ǝ��̃W�F�l���[�^�[���J������
>
>Admin �W�F�l���[�^�[�� symfony �̓����R���|�[�l���g�̃Z�b�g���g���܂��B�����R���|�[�l���g�̓L���b�V�������ɐ������ꂽ�A�N�V�����ƃe���v���[�g�A�e�[�}�̎g�p�A�e���v���[�g�̃e���v���[�g�̉�͂����������܂��B
>
>���̂��Ƃ� symfony �������̃W�F�l���[�^�[�Ƃ͎��Ă���������͊��S�ɈقȂ�Ǝ��̃W�F�l���[�^�[����邽�߂̂��ׂẴc�[����񋟂��邱�Ƃ��Ӗ����܂��B���W���[���̐����� `sfGeneratorManager` �N���X�� `generate()` ���\�b�h�ŊǗ�����܂��B���Ƃ��΁A�Ǘ���ʂ𐶐����邽�߂ɁAsymfony �͓����ł��̃R�[�h���Ăяo���܂�:
>
>     [php]
>     $manager = new sfGeneratorManager();
>     $data = $manager->generate('sfPropelGenerator', $parameters);
>
>�Ǝ��̃W�F�l���[�^�[���J���������ꍇ�A`sfGeneratorManeger` �N���X�� `sfGenerator` �N���X�� API �h�L�������g�����āA`sfModelGenerator` �N���X�� `sfPropelGenerator` �N���X���Ƃ��Ă��������B

�܂Ƃ�
----

�o�b�N�G���h�̃A�v���P�[�V�����������I�ɐ����������ꍇ�A��{�͂悭��`���ꂽ�X�L�[�}�ƃI�u�W�F�N�g���f���ł��B�Ǘ���ʂ̃J�X�^�}�C�Y�ɂ���Đ������ꂽ���W���[���̃J�X�^�}�C�Y�̑唼�͐ݒ��ʂ��čs���܂��B

`generator.yml`�t�@�C���͐������ꂽ�o�b�N�G���h�̃v���O���~���O�ɂ����Ē��S�I�Ȗ������ʂ����܂��B���̃t�@�C���ɂ���ē��e�A�@�\�A`list`�A`new` �� `edit` �r���[�̌����ڂ����S�ɃJ�X�^�}�C�Y�ł��܂��B�܂� PHP �R�[�h����s���������ɁA�t�B�[���h���x���A�c�[���`�b�v�A�t�B���^�[�A�\�[�g�̏��ԁA�y�[�W�̃T�C�Y�A���̓^�C�v�A�O���̃����[�V�����A�J�X�^���C���^���N�V�����A�ƃN���f���V������ YAML �Œ��ڊǗ��ł��܂��B

Admin �W�F�l���[�^�[���K�v�ȋ@�\���l�C�e�B�u�ɃT�|�[�g���Ȃ��ꍇ�A�A�N�V�������I�[�o�[���C�h���镔���e���v���[�g�t�B�[���h�Ƌ@�\�͊��S�Ȋg������񋟂��܂��B����ɉ����āA�e�[�}�̃��J�j�Y���̂������ŁAAdmin �W�F�l���[�^�[�̃��J�j�Y���ւ̓K�����@���ė��p�ł��܂��B
