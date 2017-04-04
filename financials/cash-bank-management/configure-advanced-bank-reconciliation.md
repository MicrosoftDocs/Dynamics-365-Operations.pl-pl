---
title: "Zaawansowanego uzgodnienia konta bankowego — omówienie"
description: "Zaawansowane uzgadnianie konta bankowego pozwala na importowanie wyciągów bankowych elektronicznych i automatycznie uzgadniać z transakcjami bankowymi w usłudze Microsoft Dynamics 365 dla operacji.  Ten artykuł wyjaśnia procesy konfigurowania na potrzeby uzgadniania."
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
translationtype: Human Translation
ms.sourcegitcommit: 3b16ef53f9fb57a6663db0be1f7e0a57471db2fb
ms.openlocfilehash: c2fc9e858f61d7d0122393bbf306ba64ac3659b8
ms.lasthandoff: 03/31/2017


---

# <a name="advanced-bank-reconciliation-overview"></a>Zaawansowanego uzgodnienia konta bankowego — omówienie

Zaawansowane uzgadnianie konta bankowego pozwala na importowanie wyciągów bankowych elektronicznych i automatycznie uzgadniać z transakcjami bankowymi w usłudze Microsoft Dynamics 365 dla operacji.  Ten artykuł wyjaśnia procesy konfigurowania na potrzeby uzgadniania.  

Istnieje wiele elementów, które muszą zostać skonfigurowane przed użyciem funkcji uzgodnienia bankowego zaawansowane. Aby uzyskać więcej informacji na temat konfigurowania import wyciągu z konta, zobacz [skonfigurować proces importowania wyciągu bankowego](set-up-advanced-bank-reconciliation-import-process.md).  Wymagania dotyczące Konfigurowanie procesu uzgadniania są wyszczególnione poniżej.

## <a name="transaction-codes"></a>Kody transakcji
Kody transakcji może służyć jako część reguły uzgadniania wyciągów bankowych.  Aby dopasować te same typy transakcji między 365 Dynamics dla operacji i wyciągu bankowym pomoże kody transakcji.  Aby dokonać tego rodzaju dopasowania, należy najpierw zdefiniować typy transakcji używany dla transakcji bankowych od 365 Dynamics dla operacji, a następnie mapowania tych typów kody transakcji wyciągu używany przez bank.  Typy transakcji dla usługi Dynamics 365 dla transakcji bankowych operacje są definiowane na **typ transakcji bankowej** strony.  Jest to również, gdzie zdefiniować konta głównego używanego do księgowania skojarzonych z tym typem transakcji. 

Po zdefiniowaniu swój 365 Dynamics dla kodów transakcji operacji Banku, następnie te mapowania do kody transakcji używane w Twoich wyciągach bankowych elektronicznych.  Ten proces mapowania odbywa się za pomocą **mapowanie kodu transakcji** strony.  Mapowanie kodu transakcji jest wypełniane osobno dla każdego konta bankowego.

## <a name="matching-rules-and-matching-rule-sets"></a>Reguły uzgadniania i zestawy reguł uzgadniania
Reguły dopasowywania umożliwiają definiowanie kryteriów dla automatycznego uzgodnienie 365 Dynamics dla transakcji bankowych operacji i transakcji wyciągu bankowego.  Konfigurowanie reguł dopasowania odbywa się na **reguły uzgadniania wyciągów** strony.  Aby uzyskać więcej informacji, zobacz [skonfigurować reguły uzgadniania wyciągów bankowych](set-up-bank-reconciliation-matching-rules.md). 

Zestaw reguł uzgadniania są używane do definiowania grupy reguł dopasowania, które są uruchamiane w kolejności podczas procesu uzgodnienia bankowego.  Zestaw reguł uzgadniania są skonfigurowane na **zestawy reguł uzgadniania wyciągów** strony.

## <a name="cash-and-bank-management-parameters"></a>Parametry modułu Zarządzanie gotówką i bankami
Liczba parametrów są specyficzne dla procesu uzgadniania zaawansowane banku na **parametry zarządzania gotówką i bankami** strony.  **Pokaż kwota wiersza wyciągu w debetu/kredytu** zmienia widok kwot na **wyciąg bankowy** strony.  Jeśli ta opcja jest zaznaczona, w kolumnach kredytu i debetu oddzielnych pojawi się kwoty transakcji wyciągu bankowego.  Jeśli nie jest zaznaczone, kwoty transakcji wyciągu bankowego pojawi się w kolumnie pojedyncza kwota z odpowiedni znak. 

Opcje sprawdzania poprawności ustawione na stronie parametry zastąpić wybrane opcje ustawiać reguł dopasowania.  Na przykład nie można ręcznie lub automatycznie dopasować dokumenty poza różnica dat ustawiona na stronie parametry.  Ponadto jeśli opcja **Sprawdź poprawność mapowania typów transakcji** jest zaznaczona, typy transakcji musi być mapowany między 365 Dynamics dla transakcji bankowej operacji i transakcji wyciągu bankowego w kolejności dla transakcji można ręcznie lub automatycznie dopasować. 

Należy także skonfigurować niezbędne sekwencje numerów na **parametry zarządzania gotówką i bankami** strony.  Na **Number sequences** karcie zestaw kodów sekwencji numerów do pobrania **uzgodnienia identyfikator, identyfikator instrukcji, identyfikator uzgodnienia i Bank** odwołania.

## <a name="bank-account-reconciliation-options"></a>Opcje uzgadniania konta bankowego
Należy najpierw włączyć zaawansowane uzgadnianie konta bankowego dla konta bankowego.  Dostępnych jest kilka dodatkowych opcji na **konta bankowego** strona po włączeniu funkcji uzgodnienia bankowego zaawansowane. 

**Wyciągi bankowe użycia jako potwierdzenia płatności elektronicznych** funkcjonalność łączy w sobie funkcje uzgodnienia bankowego o statusie płatności elektronicznych.  Gdy ta opcja jest włączona, dokument bankowy zostanie utworzone automatycznie dla płatności elektronicznych stan jest ustawiony na **wysłane**.  Ponadto zostanie zaktualizowany stan płatności elektronicznych z **wysłane** do **odebrane** po dopasowaniu płatności, uzgodnione i zaksięgowane. 

**Nazwy konta bankowego w instrukcji** pole jest to nazwa używana dla danego konta bankowego na Twoich wyciągach bankowych elektronicznych.  Ta nazwa jest używana podczas określania transakcji, które do importowania dla konta bankowego z instrukcji, która może zawierać informacje dla wielu kont bankowych. 

Opcja **Uzgodnij po imporcie** automatycznie będzie sprawdzanie poprawności wyciągu bankowego, tworzyć nowe uzgodnienia bankowego i arkusza i uruchomić domyślnego zestawu reguł uzgadniania.  Ta funkcja automatyzuje proces do momentu transakcji, które muszą zostać dopasowany ręcznie.  Ustawienie dla konta bankowego będzie domyślnie podczas importowania.


