# GMD_DB
고문당 테이블 구조

USE [GMD_WMS]
GO

/****** Object:  Table [dbo].[PART_MAST]    Script Date: 2023-03-07 오전 11:09:03 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[PART_MAST](
	[PART_NO] [nvarchar](30) NOT NULL,
	[PART_NAME] [nvarchar](100) NULL,
	[PART_TYPE] [nvarchar](50) NULL,
	[SPEC] [nvarchar](50) NULL,
	[UNIT_WEIGHT] [numeric](15, 3) NULL,
	[EDIT_TIME] [varchar](19) NULL,
	[EDIT_USER] [varchar](20) NULL,
 CONSTRAINT [PK_PART_MAST] PRIMARY KEY CLUSTERED 
(
	[PART_NO] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

/****** Object:  Table [dbo].[SECTION_STAT]    Script Date: 2023-03-07 오전 11:09:03 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[SECTION_STAT](
	[SECTION_NO] [nvarchar](20) NOT NULL,
	[BARCODE_NO] [nvarchar](20) NOT NULL,
	[SEQ] [int] NOT NULL,
	[PART_NO] [nvarchar](30) NULL,
	[INOUT_TYPE] [nvarchar](20) NULL,
	[FROM_LOCA] [nvarchar](20) NULL,
	[TO_LOCA] [nvarchar](20) NULL,
	[CMD_ID] [varchar](50) NULL,
	[QTY] [numeric](18, 0) NULL,
	[REMARK] [nvarchar](1000) NULL,
	[SPLIT_YN] [nvarchar](1) NULL,
	[EDIT_TIME] [datetime] NULL,
	[EDIT_USER] [nvarchar](20) NULL,
 CONSTRAINT [PK_SECTION_STAT] PRIMARY KEY CLUSTERED 
(
	[SECTION_NO] ASC,
	[BARCODE_NO] ASC,
	[SEQ] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

/****** Object:  Table [dbo].[TAOUT]    Script Date: 2023-03-07 오전 11:09:03 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[TAOUT](
	[CMPCODE] [nvarchar](2) NOT NULL,
	[BIZDIV] [nvarchar](3) NOT NULL,
	[AOUTNO] [nvarchar](20) NOT NULL,
	[FACCODE] [nvarchar](6) NULL,
	[AOUTDT] [nvarchar](8) NULL,
	[DATAMAKE] [nvarchar](20) NULL,
	[ITEMGB] [nvarchar](6) NULL,
	[LOCGB] [nvarchar](6) NULL,
	[AOUTORDER] [nvarchar](6) NULL,
	[AOUTGB] [nvarchar](6) NULL,
	[AOUTMA] [nvarchar](6) NULL,
	[AOUTGATE] [nvarchar](6) NULL,
	[AOUTROUTE] [nvarchar](6) NULL,
	[ITEMCODE] [nvarchar](30) NULL,
	[QTY] [numeric](18, 0) NULL,
	[USEQTY] [numeric](18, 0) NULL,
	[REMAINYN] [nchar](1) NULL,
	[LOCNO] [nvarchar](20) NULL,
	[LOCNUM] [nvarchar](20) NULL,
	[AINTNO] [nvarchar](20) NULL,
	[AOUTRQNO] [nvarchar](20) NULL,
	[ORDERNO] [nvarchar](14) NULL,
	[WONO] [nvarchar](14) NULL,
	[WOSEQ] [int] NULL,
	[MACNO] [nvarchar](10) NULL,
	[FORWARDRQ] [nvarchar](14) NULL,
	[DELIVNO] [nvarchar](14) NULL,
	[OUTNO] [nvarchar](14) NULL,
	[OUTSEQ] [int] NULL,
	[BYPASS] [nvarchar](1) NULL,
	[REMARK] [nvarchar](100) NULL,
	[ETC] [nvarchar](30) NULL,
	[BLANK_FLAG] [nvarchar](1) NULL,
	[SPLIT_QTY] [int] NULL,
	[IFYN] [nvarchar](2) NULL,
	[AOUTYN] [nchar](1) NULL,
	[INSEMPCODE] [nvarchar](10) NULL,
	[INSDT] [datetime] NULL,
	[UPEMPCODE] [nvarchar](10) NULL,
	[UPDT] [datetime] NULL,
 CONSTRAINT [PK_TAOUT] PRIMARY KEY CLUSTERED 
(
	[CMPCODE] ASC,
	[BIZDIV] ASC,
	[AOUTNO] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

/****** Object:  Table [dbo].[TAOUTRQ]    Script Date: 2023-03-07 오전 11:09:03 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[TAOUTRQ](
	[CMPCODE] [nvarchar](2) NOT NULL,
	[BIZDIV] [nvarchar](3) NOT NULL,
	[AOUTRQNO] [nvarchar](20) NOT NULL,
	[AOUTRQDT] [nvarchar](8) NULL,
	[FACCODE] [nvarchar](6) NULL,
	[DATAMAKE] [nvarchar](20) NULL,
	[ITEMGB] [nvarchar](6) NULL,
	[LOCGB] [nvarchar](6) NULL,
	[AOUTORDER] [nvarchar](6) NULL,
	[AOUTGB] [nvarchar](6) NULL,
	[AOUTMA] [nvarchar](6) NULL,
	[AOUTGATE] [nvarchar](6) NULL,
	[AOUTROUTE] [nvarchar](6) NULL,
	[ITEMCODE] [nvarchar](30) NULL,
	[QTY] [numeric](18, 0) NULL,
	[ORDERNO] [nvarchar](14) NULL,
	[WONO] [nvarchar](14) NULL,
	[WOSEQ] [int] NULL,
	[MACNO] [nvarchar](10) NULL,
	[FORWARDRQ] [nvarchar](14) NULL,
	[RQSTS] [nvarchar](6) NULL,
	[BYPASS] [nvarchar](1) NULL,
	[EXPOUTTIME] [nvarchar](10) NULL,
	[REMARK] [nvarchar](100) NULL,
	[ETC] [nvarchar](30) NULL,
	[TAOUTYN] [nvarchar](1) NULL,
	[IFYN] [nvarchar](2) NULL,
	[INSEMPCODE] [nvarchar](10) NULL,
	[INSDT] [datetime] NULL,
	[UPEMPCODE] [nvarchar](10) NULL,
	[UPDT] [datetime] NULL,
 CONSTRAINT [PK_TAOUTRQ] PRIMARY KEY CLUSTERED 
(
	[CMPCODE] ASC,
	[BIZDIV] ASC,
	[AOUTRQNO] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

/****** Object:  Table [dbo].[WMS_RESHIST]    Script Date: 2023-03-07 오전 11:09:03 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[WMS_RESHIST](
	[RES_NO] [nvarchar](20) NOT NULL,
	[RES_DATE] [nvarchar](10) NULL,
	[SEQ] [int] NULL,
	[CMPCODE] [nvarchar](2) NULL,
	[BIZDIV] [nvarchar](3) NULL,
	[AINTNO] [nvarchar](20) NULL,
	[AOUTRQNO] [nvarchar](20) NULL,
	[AOUTNO] [nvarchar](20) NULL,
	[OUT_PRIORITY] [nvarchar](6) NULL,
	[ITEMGB] [nvarchar](6) NULL,
	[ITEMCODE] [nvarchar](30) NULL,
	[QTY] [numeric](18, 0) NULL,
	[LOCA_CODE] [nvarchar](10) NULL,
	[RES_TYPE] [nvarchar](10) NULL,
	[RES_STAT] [nvarchar](50) NULL,
	[LINE_POS] [int] NULL,
	[LINE_SEQ] [nvarchar](20) NULL,
	[DBL_FLAG] [nvarchar](1) NULL,
	[BLANK_FLAG] [nvarchar](1) NULL,
	[CANCEL_FLAG] [nvarchar](1) NULL,
	[RGV_CALL] [nvarchar](1) NULL,
	[EDIT_TIME] [datetime] NULL,
	[EDIT_USER] [varchar](20) NULL,
 CONSTRAINT [PK_WMS_RESHIST] PRIMARY KEY CLUSTERED 
(
	[RES_NO] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

ALTER TABLE [dbo].[PART_MAST] ADD  CONSTRAINT [DF_PART_MAST_PART_NAME]  DEFAULT ('') FOR [PART_NAME]
GO

ALTER TABLE [dbo].[PART_MAST] ADD  CONSTRAINT [DF_PART_MAST_PART_TYPE]  DEFAULT ('') FOR [PART_TYPE]
GO

ALTER TABLE [dbo].[PART_MAST] ADD  CONSTRAINT [DF_PART_MAST_SPEC]  DEFAULT ('') FOR [SPEC]
GO

ALTER TABLE [dbo].[PART_MAST] ADD  CONSTRAINT [DF_PART_MAST_UNIT_WEIGHT]  DEFAULT ((0)) FOR [UNIT_WEIGHT]
GO

ALTER TABLE [dbo].[PART_MAST] ADD  CONSTRAINT [DF_PART_MAST_EDIT_TIME]  DEFAULT (NULL) FOR [EDIT_TIME]
GO

ALTER TABLE [dbo].[PART_MAST] ADD  CONSTRAINT [DF_PART_MAST_EDIT_USER]  DEFAULT ('') FOR [EDIT_USER]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_BARCODE_NO]  DEFAULT ('') FOR [BARCODE_NO]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF__SECTION_STA__SEQ__00FFE85F]  DEFAULT ((1)) FOR [SEQ]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_PART_NO]  DEFAULT ('') FOR [PART_NO]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_INOUT_TYPE]  DEFAULT ('') FOR [INOUT_TYPE]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_FROM_LOCA]  DEFAULT ('') FOR [FROM_LOCA]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_TO_LOCA]  DEFAULT ('') FOR [TO_LOCA]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_CMD_ID]  DEFAULT ('') FOR [CMD_ID]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_QTY]  DEFAULT ((0)) FOR [QTY]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_REMARK]  DEFAULT ('') FOR [REMARK]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF__SECTION_S__SPLIT__08A10A27]  DEFAULT ('N') FOR [SPLIT_YN]
GO

ALTER TABLE [dbo].[SECTION_STAT] ADD  CONSTRAINT [DF_SECTION_STAT_EDIT_USER]  DEFAULT ('') FOR [EDIT_USER]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_FACCODE]  DEFAULT ('') FOR [FACCODE]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTDT]  DEFAULT ('') FOR [AOUTDT]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_DATAMAKE]  DEFAULT ('') FOR [DATAMAKE]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_ITEMGB]  DEFAULT ('') FOR [ITEMGB]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_LOCGB]  DEFAULT ('') FOR [LOCGB]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTORDER]  DEFAULT ('') FOR [AOUTORDER]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTGB]  DEFAULT ('') FOR [AOUTGB]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTMA]  DEFAULT ('') FOR [AOUTMA]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTGATE]  DEFAULT ('') FOR [AOUTGATE]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTROUTE]  DEFAULT ('') FOR [AOUTROUTE]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_ITEMCODE]  DEFAULT ('') FOR [ITEMCODE]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_QTY]  DEFAULT ((0)) FOR [QTY]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_USEQTY]  DEFAULT ((0)) FOR [USEQTY]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_REMAINYN]  DEFAULT (N'{''}') FOR [REMAINYN]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_LOCNO]  DEFAULT ('') FOR [LOCNO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_LOCNUM]  DEFAULT ('') FOR [LOCNUM]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AINTNO]  DEFAULT ('') FOR [AINTNO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTRQNO]  DEFAULT ('') FOR [AOUTRQNO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_ORDERNO]  DEFAULT ('') FOR [ORDERNO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_WONO]  DEFAULT ('') FOR [WONO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_WOSEQ]  DEFAULT ((0)) FOR [WOSEQ]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_MACNO]  DEFAULT ('') FOR [MACNO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_FORWARDRQ]  DEFAULT ('') FOR [FORWARDRQ]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_DELIVNO]  DEFAULT ('') FOR [DELIVNO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_OUTNO]  DEFAULT ('') FOR [OUTNO]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_OUTSEQ]  DEFAULT ((0)) FOR [OUTSEQ]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_BYPASS]  DEFAULT ('') FOR [BYPASS]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_REMARK]  DEFAULT ('') FOR [REMARK]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_ETC]  DEFAULT ('') FOR [ETC]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_BLANK_FLAG]  DEFAULT ('') FOR [BLANK_FLAG]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_SPLIT_CNT]  DEFAULT ((0)) FOR [SPLIT_QTY]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_IFYN]  DEFAULT ('') FOR [IFYN]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_AOUTYN]  DEFAULT ('N') FOR [AOUTYN]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_INSEMPCODE]  DEFAULT ('') FOR [INSEMPCODE]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_INSDT]  DEFAULT (NULL) FOR [INSDT]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_UPEMPCODE]  DEFAULT ('') FOR [UPEMPCODE]
GO

ALTER TABLE [dbo].[TAOUT] ADD  CONSTRAINT [DF_TAOUT_UPDT]  DEFAULT (NULL) FOR [UPDT]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_AOUTRQDT]  DEFAULT ('') FOR [AOUTRQDT]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_FACCODE]  DEFAULT ('') FOR [FACCODE]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_DATAMAKE]  DEFAULT ('') FOR [DATAMAKE]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_ITEMGB]  DEFAULT ('') FOR [ITEMGB]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_LOCGB]  DEFAULT ('') FOR [LOCGB]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_AOUTORDER]  DEFAULT ('') FOR [AOUTORDER]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_AOUTGB]  DEFAULT ('') FOR [AOUTGB]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_AOUTMA]  DEFAULT ('') FOR [AOUTMA]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_AOUTGATE]  DEFAULT ('') FOR [AOUTGATE]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_AOUTROUTE]  DEFAULT ('') FOR [AOUTROUTE]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_ITEMCODE]  DEFAULT ('') FOR [ITEMCODE]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_QTY]  DEFAULT ((0)) FOR [QTY]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_ORDERNO]  DEFAULT ('') FOR [ORDERNO]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_WONO]  DEFAULT ('') FOR [WONO]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_WOSEQ]  DEFAULT ((0)) FOR [WOSEQ]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_MACNO]  DEFAULT ('') FOR [MACNO]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_FORWARDRQ]  DEFAULT ('') FOR [FORWARDRQ]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_RQSTS]  DEFAULT ('') FOR [RQSTS]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_BYPASS]  DEFAULT ('') FOR [BYPASS]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_EXPOUTTIME]  DEFAULT ('') FOR [EXPOUTTIME]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_REMARK]  DEFAULT ('') FOR [REMARK]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_ETC]  DEFAULT ('') FOR [ETC]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_TAOUTYN]  DEFAULT ('N') FOR [TAOUTYN]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_IFYN]  DEFAULT ('') FOR [IFYN]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_INSEMPCODE]  DEFAULT ('') FOR [INSEMPCODE]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_INSDT]  DEFAULT (NULL) FOR [INSDT]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_UPEMPCODE]  DEFAULT ('') FOR [UPEMPCODE]
GO

ALTER TABLE [dbo].[TAOUTRQ] ADD  CONSTRAINT [DF_TAOUTRQ_UPDT]  DEFAULT (NULL) FOR [UPDT]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_CMPCODE]  DEFAULT ('') FOR [CMPCODE]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_BIZDIV]  DEFAULT ('') FOR [BIZDIV]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_AINTNO]  DEFAULT ('') FOR [AINTNO]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_AOUTRQNO]  DEFAULT ('') FOR [AOUTRQNO]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_AOUTNO]  DEFAULT ('') FOR [AOUTNO]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_OUT_PRIORITY]  DEFAULT ('') FOR [OUT_PRIORITY]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_ITEMGB]  DEFAULT ('') FOR [ITEMGB]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_ITEMCODE]  DEFAULT ('') FOR [ITEMCODE]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_QTY]  DEFAULT ((0)) FOR [QTY]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_LOCA_CODE]  DEFAULT ('') FOR [LOCA_CODE]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_RES_STAT]  DEFAULT ('') FOR [RES_STAT]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_LINE_POS]  DEFAULT ((0)) FOR [LINE_POS]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_LINE_SEQ]  DEFAULT ('') FOR [LINE_SEQ]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_DBL_FLAG]  DEFAULT ('') FOR [DBL_FLAG]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_BLANK_FLAG]  DEFAULT ('') FOR [BLANK_FLAG]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_CANCEL_FLAG]  DEFAULT ('') FOR [CANCEL_FLAG]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_RGV_CALL]  DEFAULT ('') FOR [RGV_CALL]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_EDIT_TIME]  DEFAULT (NULL) FOR [EDIT_TIME]
GO

ALTER TABLE [dbo].[WMS_RESHIST] ADD  CONSTRAINT [DF_WMS_RESHIST_EDIT_USER]  DEFAULT ('') FOR [EDIT_USER]
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST', @level2type=N'COLUMN',@level2name=N'PART_NO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'품목명' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST', @level2type=N'COLUMN',@level2name=N'PART_NAME'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'분품목구' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST', @level2type=N'COLUMN',@level2name=N'PART_TYPE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'품목규격' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST', @level2type=N'COLUMN',@level2name=N'SPEC'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'단위당무게' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST', @level2type=N'COLUMN',@level2name=N'UNIT_WEIGHT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'최종변경' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST', @level2type=N'COLUMN',@level2name=N'EDIT_TIME'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'변경자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST', @level2type=N'COLUMN',@level2name=N'EDIT_USER'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'품목 마스터' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'PART_MAST'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'회사구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'CMPCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'사업부구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'BIZDIV'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'창고출고번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'공장구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'FACCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'창고출고일자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTDT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'데이터생성위치' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'DATAMAKE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'품목구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'ITEMGB'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'창고구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'LOCGB'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고우선순위' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTORDER'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고구분 (정상,기타)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTGB'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고구분 (자동,반자동,수동)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTMA'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고게이트' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTGATE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고경로' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTROUTE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'품목코드' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'ITEMCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수량' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'QTY'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'사용수량' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'USEQTY'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'잔량여부' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'REMAINYN'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'창고번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'LOCNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'창고위치코드' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'LOCNUM'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'창고입고번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AINTNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고요청번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'AOUTRQNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수주번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'ORDERNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'작업지시번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'WONO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'작업지시순번' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'WOSEQ'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고요청설비' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'MACNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'출하지시번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'FORWARDRQ'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'제품출고번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'DELIVNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'자재출고번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'OUTNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'저재출고번호순번' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'OUTSEQ'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'비고' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'REMARK'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'기타' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'ETC'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'입력자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'INSEMPCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'입력일' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'INSDT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수정자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'UPEMPCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수정일' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT', @level2type=N'COLUMN',@level2name=N'UPDT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'자동창고 출고' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'회사구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'CMPCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'사업부구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'BIZDIV'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고요청번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'AOUTRQNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고요청일자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'AOUTRQDT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'공장구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'FACCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'데이터생성위치' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'DATAMAKE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'품목구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'ITEMGB'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'창고구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'LOCGB'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고우선순위' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'AOUTORDER'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고구분 (정상,기타)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'AOUTGB'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고구분 (자동,반자동,수동)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'AOUTMA'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고게이트' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'AOUTGATE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고경로' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'AOUTROUTE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'품목코드' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'ITEMCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수량' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'QTY'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수주번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'ORDERNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'작업지시번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'WONO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'작업지시순번' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'WOSEQ'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고요청설비' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'MACNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출하지시번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'FORWARDRQ'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'출고요청진행상태' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'RQSTS'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'예상출고시작시간' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'EXPOUTTIME'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'비고' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'REMARK'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'기타' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'ETC'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'입력자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'INSEMPCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'입력일' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'INSDT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수정자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'UPEMPCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'수정일' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ', @level2type=N'COLUMN',@level2name=N'UPDT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_DESCRIPTION', @value=N'자동창고 출고요청' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TAOUTRQ'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'예약번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'RES_NO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'예약일자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'RES_DATE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'순번' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'SEQ'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'회사구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'CMPCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'사업부구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'BIZDIV'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'창고입고번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'AINTNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'출고요청번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'AOUTRQNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'창고출고번호' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'AOUTNO'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'출고우선순위' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'OUT_PRIORITY'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'품목구분' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'ITEMGB'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'품목코드' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'ITEMCODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'수량' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'QTY'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'창고위치코드' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'LOCA_CODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'예약타입 (입고/출고)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'RES_TYPE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'예약상태 (신규/진행중)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'RES_STAT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'최종변경' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'EDIT_TIME'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'변경자' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST', @level2type=N'COLUMN',@level2name=N'EDIT_USER'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'WMS 예약지시' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'WMS_RESHIST'
GO


USE [GMD_AGV_IF]
GO

/****** Object:  Table [dbo].[TQ_CMD]    Script Date: 2023-03-07 오전 11:08:02 ******/
SET ANSI_NULLS ON
GO

SET QUOTED_IDENTIFIER ON
GO

CREATE TABLE [dbo].[TQ_CMD](
	[SITE_CODE] [char](1) NOT NULL,
	[CMD_ID] [char](21) NOT NULL,
	[WCS_JOB_ID] [varchar](30) NULL,
	[SEQ] [int] NULL,
	[PRIORITY] [int] NULL,
	[LOAD_PORT_ID] [varchar](20) NULL,
	[UNLOAD_PORT_ID] [varchar](20) NULL,
	[CARRIER_ID] [varchar](21) NULL,
	[RESERVED_AGV_NAME] [char](5) NULL,
	[ABORT_CMD_YN] [char](1) NULL,
	[ACS_RECV_YN] [char](1) NULL,
	[ASSIGN_AGV_NAME] [char](5) NULL,
	[START_DT] [varchar](19) NULL,
	[COMPLETE_DT] [varchar](19) NULL,
	[COMPLETE_YN] [char](1) NULL,
	[FAULT_YN] [char](1) NULL,
	[DESC] [varchar](200) NULL,
	[WMS_YN] [char](1) NULL,
 CONSTRAINT [PK_TQ_CMD] PRIMARY KEY CLUSTERED 
(
	[SITE_CODE] ASC,
	[CMD_ID] ASC
)WITH (PAD_INDEX = OFF, STATISTICS_NORECOMPUTE = OFF, IGNORE_DUP_KEY = OFF, ALLOW_ROW_LOCKS = ON, ALLOW_PAGE_LOCKS = ON) ON [PRIMARY]
) ON [PRIMARY]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_WCS_JOB_ID]  DEFAULT ('') FOR [WCS_JOB_ID]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_SEQ]  DEFAULT ((1)) FOR [SEQ]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_PRIORITY]  DEFAULT ((0)) FOR [PRIORITY]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_LOAD_PORT_ID]  DEFAULT ('') FOR [LOAD_PORT_ID]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_UNLOAD_PORT_ID]  DEFAULT ('') FOR [UNLOAD_PORT_ID]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_CARRIER_ID]  DEFAULT ('') FOR [CARRIER_ID]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_RESERVED_AGV_NAME]  DEFAULT ('') FOR [RESERVED_AGV_NAME]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_ABORT_CMD_YN]  DEFAULT ('') FOR [ABORT_CMD_YN]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_ACS_RECV_YN]  DEFAULT ('') FOR [ACS_RECV_YN]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_ASSIGN_AGV_NAME]  DEFAULT ('') FOR [ASSIGN_AGV_NAME]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_START_DT]  DEFAULT ('') FOR [START_DT]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_COMPLETE_DT]  DEFAULT ('') FOR [COMPLETE_DT]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_COMPLETE_YN]  DEFAULT ('') FOR [COMPLETE_YN]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_FAULT_YN]  DEFAULT ('') FOR [FAULT_YN]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_DESC]  DEFAULT ('') FOR [DESC]
GO

ALTER TABLE [dbo].[TQ_CMD] ADD  CONSTRAINT [DF_TQ_CMD_WMS_YN]  DEFAULT ('N') FOR [WMS_YN]
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'''G'' 고정' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'SITE_CODE'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'명령ID (AUTOyyyyMMddHHmmssfff)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'CMD_ID'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'잡ID (WCS에서 관리하는 ID)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'WCS_JOB_ID'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'우선순위 (0~99)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'PRIORITY'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'적재포트 (LOAD_PORT_1)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'LOAD_PORT_ID'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'이재포트 (UNLOAD_PORT_3)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'UNLOAD_PORT_ID'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'팔레트ID (''PLT01'')' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'CARRIER_ID'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'예약 AGV (''AGV01'')' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'RESERVED_AGV_NAME'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'명령취소여부' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'ABORT_CMD_YN'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'수신여부' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'ACS_RECV_YN'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'할당 AGV' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'ASSIGN_AGV_NAME'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'시작일시' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'START_DT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'완료일시' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'COMPLETE_DT'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'명령완료여부' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'COMPLETE_YN'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'명령실패여부' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'FAULT_YN'
GO

EXEC sys.sp_addextendedproperty @name=N'MS_Description', @value=N'설명 - DEBUG용 (LOAD중 명령취소불가)' , @level0type=N'SCHEMA',@level0name=N'dbo', @level1type=N'TABLE',@level1name=N'TQ_CMD', @level2type=N'COLUMN',@level2name=N'DESC'
GO


