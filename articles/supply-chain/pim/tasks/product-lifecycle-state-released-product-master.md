---
title: Przypisywanie cyklu życia produktu do zwolnionego produktu głównego
description: W tej procedurze pokazano sposób przypisywania stanu cyklu życia produktu do zwolnionego produktu głównego i jego wariantów.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 217bab38544c2794d2e57410f8c2a979605106b0
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567014"
---
# <a name="assign-a-product-lifecycle-state-to-a-released-product-master"></a>Przypisywanie cyklu życia produktu do zwolnionego produktu głównego

[!include [banner](../../includes/banner.md)]

W tej procedurze pokazano sposób przypisywania stanu cyklu życia produktu do zwolnionego produktu głównego i jego wariantów. Warunek wstępny: przed odtworzeniem tego przewodnika zadania należy najpierw odtworzyć przewodnik zadania „Tworzenie nowego stanu cyklu życia produktu”, aby się upewnić, że dostępny jest co najmniej jeden utworzony stan cyklu życia produktu.


## <a name="find-a-released-product-master"></a>Znajdowanie zwolnionego produktu głównego
1. Przejdź do Zarządzanie informacjami o produktach > Produkty > Zwolnione produkty.
2. Na liście znajdź i zaznacz odpowiedni rekord.

> [!NOTE]
> Produkt główny zawiera podtyp produktu Produkt główny.  

## <a name="update-the-lifecycle-state"></a>Aktualizacja stan cyklu życia
1. Kliknij przycisk Edytuj.
2. W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.
3. Kliknij przycisk Zapisz.
4. Kliknij przycisk Tak.

> [!NOTE]
> W przypadku zaznaczenia opcji Tak wszystkie powiązane zwolnione warianty produktu o takim samym stanie początkowym, jak zwolniony produkt główny, również zostaną zaktualizowane z godnie z nowym stanem cyklu życia produktu. W przypadku zaznaczenie opcji Nie wszystkie warianty zachowają swój rzeczywisty stan. Warianty ze stanem cyklu życia produktu innym niż stan zwolnionego produktu głównego nie zostaną zaktualizowane.  

## <a name="verify-the-lifecycle-state-of-the-variants"></a>Sprawdzanie stan cyklu życia wariantów
1. Kliknij warianty zwolnionego produktu.

> [!NOTE]
> Należy zauważyć, że wszystkie warianty odziedziczyły wybrany stan cyklu życia ze zwolnionego produktu głównego.  

2. Na liście oznacz wybrany wiersz.
3. W polu Stan cyklu życia produktu wprowadź lub wybierz wartość.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]