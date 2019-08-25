---
layout: post
title:  "When Bioinformatics meets lymphoma/leukemia: Genomics + DLBCL"
date:   2019-05-12
---

�ڦb�{�ɯf�z��L�o�}�߷��F�A�]���ڬݨ� Bioinformatics �M��Ǥ@�_�o�ͪ��a��N�O�o�̡C�{�ɯf�z��̤j���~�Ȥ��@�N�O�����E�_��G�쪺�f�A�ҥH�n�ݫܦh��]���F��A���Y�Ϩ�F�{�b�A�j���������l�E�_���٬O�a Karyotyping�BFISH�Bmicroarray�b�i��ANext generation sequencing ���F��n�X�����O�@��`�����Ʊ��A�i��O�Ҽ{������A�]�i��O�S���H�i�H���R�����C

��ı�o Sequencing �i�H���ڭ̪���o�ǶǲΪ���k�h�o�ܦh�A���o��h�S����k�^�������D�A���K���i��N�æb�̭��a�I�ҥH�ڷQ�n�Ӭݬ� Genomics �|�����ܥ��Ӧ�G�e�f���v���O�H

# �e�f�GDiffuse Large B Cell Lymphoma
���Ѭݪ��峹�����`���e�f�s�� Diffuse Large B Cell Lymphoma (DLBCL)�A�O�̱`�����@�� Lymphoma�CDLBCL �b�Ҧ� Lymphoma �̭�����O���a���A�j�������H�b�g�L�зǪv����R-CHOP �H�᳣�i�H�����A���O�L�̵o�{���@�s�f�H�S�O�e���_�o�A�ӥB�_�o�H��e�f�N�|�ܱo��������C�L�h���H�ΰ�]����{�� DLBCL �A������s�A�s ABC-DLBCL �M GCB-DLBCL�A���Y�ϳo�ˡA�٬O�S��k��f�H���ӫ��� outcome ���ܦn�����s�C

# ������n���s�H
��ı�o�A�p�G�i�H���X�@�s���a�� DLBCL�A����γ\�ڭ̥i�H�X�o�M��� R-CHOP �٭n��F�`���v���p�e�A���o�@�s�H���Ψ���̫ᨺ�@�B�C

# �Τ����Ƥ��s�H
�o�g�D�n�ϥΪ��O Genomic data�A�N�O DNA �ǦC�C�L�ä��O�����]�鳣�w�ǡA�u���w Whole exome�A�]�N�O�|�ܥX�J�ս誺�����C���w����]�骺��]�i��O�]���ӶQ�A�]�i��]���ڭ̹藍�ܦ��J�ս誺�ǦC�F�Ѥ��h�A�ҥH�w�X�Ӫ��F�褣�@�w����R�X����C

# �����R Genomic ����ơH

## Step 0: �B�z�w�Ǫ����

### Quality control, filtering, mapping to reference genome

### ��������w�L�ְ��L(!)

## Step 1: ��X�y�� DLBCL ���a�a��]

### ������n�o�򰵡H
�p�G���]�ڭ̧�Ҧ��H���Ҧ���]������A��X���@�˪��a��A�γo�Ǥ��P���a��Ӱ����s�A����|�U���ܦh���T�C�]���H��H���ӴN���ܦh���@�˪��a��A���H�l�Ů�N�|�D�A���H�Y�@�j��]���|�D�C�ڷQ�����O��**�ä��O�C�@�Ӥ��P���a��A���M DLBCL �����Y�B���O�a�a��]**�A�ҥH�ڭ̥����n�n�n���D�X�u���M DLBCL ��������]�̡A�A�Ӱ����s�A�o�˷|����ΡC

### �n����H
�ܪ�ı����k�N�O�ΰʪ��βӭM�A��Y�Ӱ�]�ܫܦh�A���ܤ����A�ݬݽַ|�o���g�C�i�O��]�ܦh�A�ܪ��覡�ܦh�A�A�i�H��L�����ܤ����A�]�i�H�u�ܱ��X���I�A�o�˪��ܹ���û����������C�ҥH�ڭ̥����n�ιq���h��X�u�̦��i��v�����ǡC

��ı�o�o�g�峹���G�I���@�N�O�L���]���覡�A���ڭ̨Ӭݬ��a�a��]�i��|�����ǯS�x�G
1. �a�a��]�|�֦��u��Ѫ����ܡv�A�]���o�ǯf�H���O�@�X�ʹN�� DLBCL�C�n��X���Ǭ��ܬO��Ѫ��A�N��ڭ̭n�M�f�H���`����´����C(To find somatic mutations)
2. �a�a��]���L��]�֦���h���ܡC(Cancer associated genes tend to have higher mutational frequencies)
3. �o�Ǭ��ܦb�J�� 3D ���c�W���|�E���b�@�_�A�]�� Sequence - Structure - Function/Phenotype�C�o�ͦb���n��m���F��A���{���|�����n���v�T�C

1. ��X��Ѫ�����(Somatic mutation)�A�ݭn�����`��´�t��C
�i���b�o�Ӭ�s�����O�C�ӤH�������쥿�`��´������A�b�o�˪����p�U�L�̹G���o�w�u�n�ϥΨ�L�����`���鰵����A�åB�����`���������ܲ�(Germline mutation)�C
2. ��X��۸��h���ܪ���]�C
�L�̨ϥΪ��u��s [MutSigCV](https://www.nature.com/articles/nature12213#methods-summary)�A�j�N�ӻ��A�]���C�ӤH�B�C�����g�B�C�� genome region �B��]����{�q�������P�����ܾ��v�A�o�� tool �b�����ƴN�O�����P�H�B���P���g�B���P genomic region �����P���I�����ܲv�A�Ǧ���X�u�����ܦh����]�C
3. ��X�b�J�յ��c�W����������
�L�̨ϥΪ��u��s [CLUMP](https://www.pnas.org/content/112/40/E5486.long#sec-14)�A�|��X�C�� Protein ������ residue �����������h�����C�Z�����ϥά��ܪ��W�v�[�v�C�ܩ�h�u�����v�s�������H���o�� tool ���H���ͤF�h���u���ì��ܡv���� data�A�èϥγo���� data �]�p��X �����סA�A�βέp�h��X��۪���(FDR)�C

�ݨ�o�̧A�i��ı�o�A��ť�A���I�d���n��쪺�ڥ����O�@��U���C�ҥH�L�̦���񤧫e�w���� tumor supressor gene, oncogene�A�]���F�ܦh�ͪ����Q�סC

### �a�a��]�����ܥ����ӡH
�����򥿱`�� genome ���|�ֿn�o��h���ܡH�]�� cancer cell �̭��ܦh DNA repair mechanism �a���B�]���i�঳�S�O�h�� Reactive Oxygen Species�A�b B cell lymphoma ���٦��@�ӯS�O���s�� Somatic hypermutation(SHM)�A�o�ǳ��O�|�����ܲv�󰪪��C

�C�@�زֿn���ܪ��覡�����L�̳��w���ܪk�A�i���䤤���ͪ��ƾǾ��঳���AĴ�p�� AID (�䤤�@�� SHM)�N���w�b�Y�� motif �� deamination �������C[Signature Analyzer](https://www.nature.com/articles/ncomms9866)�����F 30 �� CLL genome�A���եh�ѥX�o�� pattern�C

���ڤ@�}�l�ܺôb�|����L�̭n���o�˪����R�A�N�⪾�D�Y���a�a��]�O�]�� somatic hypermutation �t�@�ӬO�]���O�� mechanism ������˪����U�ܡH

### �a�a��]���O�u������
�a�a��]���ҥH�a�A���u�O�]�����I�����ܡA�٦��i��O�]���_���B�V���骺���աB�άO�����ܦh�������C�o�g�۸���H�e���P���N�O�L���n�A�h���ܲ��A�Ӥ��u�M�`�b�I���ܡC�ܩ�n���b�H������Ƥ�½�X�o���ܲ��B�ӥB�n�i�D�ڭ̬O�u���@���V���馳�ܡA�٬O������ܡA�άO�T������(���g�� karyotype �`�`���ǩǪ�)�A�N�n����U�� variant calling tool�C

## Step 2: ���s
��ƳB�z�q�`�O�̳·еM��L�᪺�B�J(���O�ܭ��n�C����)�A���L��o�̧ڭ̤w�g�i�H�e�X�@�i�W�j���F�G

## Step 3: ���s

### ���s����k

### �ƥX�C�@�Ӥ��s����]���a����

## Step 4: �ھڤ��s�w���s��

# �L�̪��o�{

# �i�঳�����D

# ��ı�o�ܥi�����a��

# ���Ψ��{�ɪ��i���