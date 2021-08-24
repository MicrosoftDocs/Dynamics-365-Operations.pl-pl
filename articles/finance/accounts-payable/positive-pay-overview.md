---
title: Płatności dodatnie — omówienie
description: Ten artykuł zawiera informacje o aparacie płatności dodatnich. Umożliwia on generowania elektronicznej listy czeków, które można okazywać bankowi.
author: panolte
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePaySummary
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "88463"
- intro-internal
ms.assetid: 1e3a39d3-f9b3-4073-9730-c96a607243e2
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 5a428a945be8fd6b570cc4ad61e1f1d285b2a0205e72aab2418c300bdb967da3
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6737338"
---
# <a name="positive-pay-overview"></a>Płatności dodatnie — omówienie

[!include [banner](../includes/banner.md)]

Ten artykuł zawiera informacje o aparacie płatności dodatnich. Umożliwia on generowania elektronicznej listy czeków, które można okazywać bankowi. 

Płatności dodatnie służą do generowania elektronicznej listy czeków, które można okazywać bankowi. Pliki płatności dodatnich ułatwiają bankom zapobieganie oszustwom związanym z czekami. Administrator konfiguruje płatności dodatnie w celu generowania elektronicznej listy czeków za każdym razem, gdy czeki są drukowane. Następnie gdy czek jest przedstawiany bankowi, bank porównuje go z wcześniej wysłaną listą czeków. Jeśli czek pasuje do czeku na liście, wówczas bank rozlicza czek. Jeśli czek nie pasuje do czeku na liście, bank wstrzymuje czek w celu sprawdzenia.

Płatność dodatnia jest też nazywana SafePay. 

Pliki płatności dodatnich mogą zawierać poufne informacje na temat odbiorców płatności i kwot czeków. W związku z tym musisz podjąć odpowiednie środki bezpieczeństwa od momentu wygenerowania plików aż do ich odbioru przez bank. Pliki płatności dodatnich są pobierane zgodnie z instrukcjami pobierania odpowiednimi dla przeglądarki internetowej. 

Pliki płatności dodatnich tworzy się za pomocą jednostek danych. Aby można było wygenerować pliku płatności dodatnich, należy skonfigurować formaty przekształceń kodu XML, które dokonują translacji danych do formatu czytelnego dla banku. 

Dla każdego konta bankowego, dla którego chcesz wygenerować informacje o płatnościach dodatnich, należy przypisać format płatności dodatnich. Po wygenerowaniu płatności można wygenerować plik płatności dodatnich dla pojedynczej firmy i pojedynczego konta bankowego. Alternatywnie można generować pliki płatności dodatnich dla wielu firm i kont bankowych równocześnie. 

Po zapłaceniu czeków wymienionych w pliku płatności dodatnich, otrzymasz numer potwierdzenia z banku. Następnie można potwierdzić plik płatności dodatnich w systemie. 

Jeśli trzeba zmodyfikować plik płatności dodatnich, można go wycofać. Wtedy dla każdego czeku w pliku płatności dodatnich jest resetowane pole wskazujące, czy czek jest uwzględniony w pliku płatności dodatnich.

Aby uzyskać więcej informacji, zobacz [Konfigurowanie i generowanie plików płatności dodatnich](set-up-generate-positive-pay-files.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]