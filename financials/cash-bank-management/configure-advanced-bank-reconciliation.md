---
title: "Zaawansowanego uzgodnienia konta bankowego — omówienie"
description: "Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych oraz ich automatyczne uzgadnianie z transakcjami bankowymi w programie Microsoft Dynamics 365 for Operations.  Ten artykuł wyjaśnia procesy konfigurowania na potrzeby uzgadniania."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 6c6b171fbba90b02b80c70783ecfd9ab57beb96d
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Zaawansowanego uzgodnienia konta bankowego — omówienie

[!include[banner](../includes/banner.md)]


Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych oraz ich automatyczne uzgadnianie z transakcjami bankowymi w programie Microsoft Dynamics 365 for Operations.  Ten artykuł wyjaśnia procesy konfigurowania na potrzeby uzgadniania.  

Istnieje wiele elementów, które muszą zostać skonfigurowane przed używaniem funkcji zaawansowanego uzgadniania konta bankowego. Aby uzyskać więcej informacji na temat konfigurowania importu wyciągu bankowego, zobacz [Konfigurowanie procesu importowania wyciągu bankowego](set-up-advanced-bank-reconciliation-import-process.md).  Poniżej wyszczególniono wymagania dotyczące konfigurowania procesu uzgadniania.

## <a name="transaction-codes"></a>Kody transakcji
W regułach uzgadniania wyciągów bankowych można używać kodów transakcji.  Kody transakcji pomogą dopasowywać tylko te same typy transakcji między programem Dynamics 365 for Operations a wyciągiem bankowym.  Aby wykonać tego rodzaju dopasowanie, należy najpierw zdefiniować typy transakcji używane do transakcjach bankowych w programie Dynamics 365 for Operations, a następnie zamapować te typy na kody transakcji na wyciągach używane przez bank.  Typy transakcji bankowych w programie Dynamics 365 for Operations definiuje się na stronie **Typ transakcji bankowej**.  Jest to również miejsce, gdzie definiujesz konto główne, które ma być używane do księgowań skojarzonych z tym typem transakcji. 

Po zdefiniowaniu kodów transakcji bankowych przewidzianych do używania w programie Dynamics 365 for Operations mapujesz te kody na kody transakcji używane w elektronicznych wyciągach bankowych.  Ten proces mapowania odbywa się na stronie **Mapowanie kodu transakcji**.  Mapowanie kodów transakcji wykonuje się osobno dla każdego konta bankowego.

## <a name="matching-rules-and-matching-rule-sets"></a>Reguły uzgadniania i zestawy reguł uzgadniania
Reguły uzgadniania umożliwiają definiowanie kryteriów automatycznego uzgadniania między transakcjami bankowymi w programie Dynamics 365 for Operations a transakcjami na wyciągach bankowych.  Konfigurowanie reguł uzgadniania odbywa się na stronie **Reguły uzgadniania wyciągów bankowych**.  Aby uzyskać więcej informacji, zobacz [Konfigurowanie reguł uzgadniania wyciągów bankowych](set-up-bank-reconciliation-matching-rules.md). 

Zestawy reguł uzgadniania służą do definiowania grup reguł uzgadniania, które są uruchamiane w kolejności podczas procesu uzgadniania konta bankowego.  Zestawy reguł uzgadniania są skonfigurowane na stronie **Zestaw reguł uzgadniania wyciągów bankowych**.

## <a name="cash-and-bank-management-parameters"></a>Parametry modułu Zarządzanie gotówką i bankami
Na stronie **Parametry modułu Zarządzanie gotówką i bankami** istnieje szereg parametrów specyficznych dla procesu zaawansowanego uzgadniania konta bankowego.  Opcja **Pokaż kwotę wiersza wyciągu w polu Debet/kredyt** zmienia widok kwot na stronie **Wyciąg bankowy**.  Jeśli ta opcja jest zaznaczona, kwoty transakcji na wyciągu bankowym będą wyświetlane osobnych kolumnach pozycji kredytowych i debetowych.  Jeśli nie jest zaznaczona, kwoty transakcji na wyciągu bankowym będą wyświetlane w jednej kolumnie kwot z odpowiednimi znakami. 

Opcje sprawdzania poprawności ustawione na stronie parametrów mają pierwszeństwo nad opcjami ustawionymi w regułach uzgadniania.  Na przykład nie można ręcznie ani automatycznie uzgadniać dokumentów poza różnicę dat ustawioną na stronie parametrów.  Ponadto jeśli jest zaznaczona opcja **Weryfikuj mapowanie typu transakcji**, typy transakcji muszą być zamapowane między transakcjami bankowymi w programie Dynamics 365 for Operations a transakcjami na wyciągu bankowym, aby transakcje można było ręcznie lub automatycznie uzgodnić. 

Należy także skonfigurować niezbędne numeracje na stronie **Parametry modułu Zarządzanie gotówką i bankami**.  Na karcie **Sekwencje identyfikatorów** ustaw kody numeracji dla odnośników pobierania **Identyfikator, Identyfikator wyciągu, Identyfikator uzgodnienia i Uzgadnianie konta bankowego**.

## <a name="bank-account-reconciliation-options"></a>Opcje uzgadniania konta bankowego
Najpierw należy włączyć zaawansowane uzgadnianie konta bankowego dla konta bankowego.  Po włączeniu funkcji Zaawansowane uzgadnianie konta bankowego uzyskasz dostęp do wielu dodatkowych opcji na stronie **Konto bankowe**. 

Funkcja **Uznaj wyciągi bankowe jako potwierdzenia płatności elektronicznych** łączy w sobie funkcje uzgadniania konta bankowego ze stanami płatności elektronicznych.  Gdy ta opcja jest włączona, dokument bankowy będzie tworzony automatycznie dla płatności elektronicznych o stanie **Wysłane**.  Ponadto po dopasowaniu, uzgodnieniu i zaksięgowaniu stan płatności elektronicznej jej stan zostanie zaktualizowany z **Wysłane** na **Odebrane**. 

Pole **Nazwa konta bankowego na wyciągach** zawiera nazwę używaną dla konta bankowego na elektronicznych wyciągach bankowych.  Ta nazwa jest wykorzystywana podczas ustalania konta bankowego, którego transakcje mają zostać zaimportowane z wyciągu mogącego zawierać informacje dla wielu kont bankowych. 

Opcja **Uzgodnij po imporcie** powoduje automatyczne sprawdzanie poprawność wyciągu bankowego, tworzenie nowego uzgodnienia konta bankowego i arkusza oraz uruchomienie domyślnego zestawu reguł uzgadniania.  Ta funkcja automatyzuje proces do momentu znalezienia transakcji, które muszą zostać dopasowane ręcznie.  To ustawienie jest domyślnie włączane dla konta bankowego podczas importowania.




