---
title: Proces ustawienia zaawansowanego uzgodnienia konta bankowego
description: Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych oraz ich automatyczne uzgadnianie z transakcjami bankowymi w Microsoft Dynamics 365 Finance. Ten artykuł wyjaśnia procesy konfigurowania na potrzeby uzgadniania.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankReconciliationMatchRule, BankReconciliationMatchRuleSet
audience: Application User
ms.reviewer: roschlom
ms.custom: 98303
ms.assetid: ae071f04-f038-4b17-812d-0a241ed15521
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9f4db43f50cc279ffc6c0ae91a16378de9567dd8
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822982"
---
# <a name="advanced-bank-reconciliation-setup-process"></a>Proces ustawienia zaawansowanego uzgodnienia konta bankowego

[!include [banner](../includes/banner.md)]

Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych oraz ich automatyczne uzgadnianie z transakcjami bankowymi w Microsoft Dynamics 365 Finance. Ten artykuł wyjaśnia procesy konfigurowania na potrzeby uzgadniania.  

Istnieje wiele elementów, które muszą zostać skonfigurowane przed używaniem funkcji zaawansowanego uzgadniania konta bankowego. Aby uzyskać więcej informacji na temat konfigurowania importu wyciągu bankowego, zobacz [Konfigurowanie procesu importu zaawansowanego uzgadniania konta bankowego](set-up-advanced-bank-reconciliation-import-process.md).  Poniżej wyszczególniono wymagania dotyczące konfigurowania procesu uzgadniania.

## <a name="transaction-codes"></a>Kody transakcji
W regułach uzgadniania wyciągów bankowych można używać kodów transakcji. Kody transakcji pomogą dopasowywać tylko te same typy transakcji między usługą Finance a wyciągiem bankowym. Aby wykonać tego rodzaju dopasowanie, należy najpierw zdefiniować typy transakcji używane do transakcji bankowych w usłudze Finance, a następnie zamapować te typy na kody transakcji na wyciągach używanych przez bank. Typy transakcji bankowych dla transakcji bankowych definiuje się na stronie **Typ transakcji bankowej**. Jest to również miejsce, gdzie definiujesz konto główne, które ma być używane do księgowań skojarzonych z tym typem transakcji. 

Po zdefiniowaniu kodów transakcji bankowych mapujesz te kody na kody transakcji używane w elektronicznych wyciągach bankowych. Ten proces mapowania odbywa się na stronie **Mapowanie kodu transakcji**. Mapowanie kodów transakcji wykonuje się osobno dla każdego konta bankowego.

## <a name="matching-rules-and-matching-rule-sets"></a>Reguły uzgadniania i zestawy reguł uzgadniania
Reguły uzgadniania umożliwiają definiowanie kryteriów automatycznego uzgadniania między transakcjami bankowymi w programie Finance a transakcjami na wyciągach bankowych. Konfigurowanie reguł uzgadniania odbywa się na stronie **Reguły uzgadniania wyciągów bankowych**. Aby uzyskać więcej informacji, zobacz [Konfigurowanie reguł uzgadniania wyciągów bankowych](set-up-bank-reconciliation-matching-rules.md). 

Zestawy reguł uzgadniania służą do definiowania grup reguł uzgadniania, które są uruchamiane w kolejności podczas procesu uzgadniania konta bankowego.  Zestawy reguł uzgadniania są skonfigurowane na stronie **Zestaw reguł uzgadniania wyciągów bankowych**.

## <a name="cash-and-bank-management-parameters"></a>Parametry modułu Zarządzanie gotówką i bankami
Na stronie **Parametry modułu Zarządzanie gotówką i bankami** istnieje szereg parametrów specyficznych dla procesu zaawansowanego uzgadniania konta bankowego.  Opcja **Pokaż kwotę wiersza wyciągu w polu Debet/kredyt** zmienia widok kwot na stronie **Wyciąg bankowy**. Jeśli ta opcja jest zaznaczona, kwoty transakcji na wyciągu bankowym będą wyświetlane osobnych kolumnach pozycji kredytowych i debetowych. Jeśli nie jest zaznaczona, kwoty transakcji na wyciągu bankowym będą wyświetlane w jednej kolumnie kwot z odpowiednimi znakami. 

Opcje sprawdzania poprawności ustawione na stronie parametrów mają pierwszeństwo nad opcjami ustawionymi w regułach uzgadniania. Na przykład nie można ręcznie ani automatycznie uzgadniać dokumentów poza różnicę dat ustawioną na stronie parametrów. Ponadto jeśli jest zaznaczona opcja **Weryfikuj mapowanie typu transakcji**, typy transakcji muszą być zamapowane między transakcjami bankowymi w programie Finance a transakcjami na wyciągu bankowym, aby transakcje można było ręcznie lub automatycznie uzgodnić. 

Należy także skonfigurować niezbędne numeracje na stronie **Parametry modułu Zarządzanie gotówką i bankami**.  Na karcie **Sekwencje identyfikatorów** ustaw kody numeracji dla odnośników pobierania **Identyfikator, Identyfikator wyciągu, Identyfikator uzgodnienia i Uzgadnianie konta bankowego**.

## <a name="bank-account-reconciliation-options"></a>Opcje uzgadniania konta bankowego
Najpierw należy włączyć zaawansowane uzgadnianie konta bankowego dla konta bankowego. Po włączeniu funkcji Zaawansowane uzgadnianie konta bankowego uzyskasz dostęp do wielu dodatkowych opcji na stronie **Konto bankowe**. 

Funkcja **Uznaj wyciągi bankowe jako potwierdzenia płatności elektronicznych** łączy w sobie funkcje uzgadniania konta bankowego ze stanami płatności elektronicznych. Gdy ta opcja jest włączona, dokument bankowy będzie tworzony automatycznie dla płatności elektronicznych o stanie **Wysłane**. Ponadto po dopasowaniu, uzgodnieniu i zaksięgowaniu stan płatności elektronicznej jej stan zostanie zaktualizowany z **Wysłane** na **Odebrane**. 

Pole **Nazwa konta bankowego na wyciągach** zawiera nazwę używaną dla konta bankowego na elektronicznych wyciągach bankowych. Ta nazwa jest wykorzystywana podczas ustalania konta bankowego, którego transakcje mają zostać zaimportowane z wyciągu mogącego zawierać informacje dla wielu kont bankowych. 

Opcja **Uzgodnij po imporcie** powoduje automatyczne sprawdzanie poprawność wyciągu bankowego, tworzenie nowego uzgodnienia konta bankowego i arkusza oraz uruchomienie domyślnego zestawu reguł uzgadniania. Ta funkcja automatyzuje proces do momentu znalezienia transakcji, które muszą zostać dopasowane ręcznie. To ustawienie jest domyślnie włączane dla konta bankowego podczas importowania.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]