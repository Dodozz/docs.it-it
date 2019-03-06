---
title: "Procedura: Codificare e decodificare un'immagine TIFF"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: e89f39dedcc210aaa6917b4b964d1944673047b5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356676"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a>Procedura: Codificare e decodificare un'immagine TIFF
Gli esempi seguenti illustrano come decodificare e codificare un' [!INCLUDE[TLA#tla_tiff](../../../../includes/tlasharptla-tiff-md.md)] immagine usando le specifiche <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> e <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> oggetti.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene illustrato come decodificare un' [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] immagine usando una <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> da un <xref:System.Uri>.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a>Esempio  
 In questo esempio illustra come codificare un <xref:System.Windows.Media.Imaging.BitmapSource> in un [!INCLUDE[TLA2#tla_tiff](../../../../includes/tla2sharptla-tiff-md.md)] immagine usando un <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a>Vedere anche
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
