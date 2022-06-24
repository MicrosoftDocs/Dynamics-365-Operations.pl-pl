---
title: Konfigurowanie parametrów wynajmu (wersja zapoznawcza)
description: W tym artykule opisano ustawienia konfiguracji dotyczące wynajmu składników aktywów, takie jak informacje o zabezpieczeniach i ustawienia księgowania.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeasePostingAccounts
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: e878fa7634cfdcc6c0db19a91e771757c545505b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8895088"
---
# <a name="configure-lease-parameters"></a>Konfigurowanie parametrów wynajmu

[!include [banner](../includes/banner.md)]

Niektóre ustawienia konfiguracji wpływają na sposób działania wynajmu składnika majątku. Te ustawienia obejmują nazwy arkuszy, parametry ogólne i ustawienia profilu księgowania.

1. Przejdź do **Wynajem składnika majątku \> Ustawienia \> Parametry wynajmu składników majątku**.
2. Na karcie **Wynajmy** wybierz skróconą kartę **Ogólne**.

    Parametr **Zezwalaj na ręczną zmianę klasyfikacji** określa, czy klasyfikacja wynajmu może zostać zastąpiona przed potwierdzeniem harmonogramu płatności.

    Parametr **Partia między jednostkami** określa, czy można księgować dane w innych firmach z bieżącej firmy. Jeśli ten parametr jest włączony, można tworzyć wpisy w arkuszu dla firm, do których masz dostęp.

3. Ustawienie opcji **Zezwalaj na usuwanie potwierdzonych wynajmów** na wartość **Tak** powoduje, że wynajmy z potwierdzonymi harmonogramami płatności zostaną usunięte. Nie można usunąć wynajmów, jeśli zaksięgowane lub niezaksięgowane transakcje są skojarzone z nimi, niezależnie od ustawienia tej opcji. Nie można przywrócić rekordu wynajmu po jego usunięciu. Jeśli użytkownik przekaże jakiekolwiek rekordy usuniętego wynajmu, ręcznie lub za pośrednictwem jednostek danych, przekazane informacje są traktowane jako nowe, a nie jako aktualizacje istniejącego wynajmu.

    Jeśli ta opcja zostanie ustawiona na wartość **tak**, a typ przejścia księgi to **Skumulowana opcja A lub B**, system ustawi wartość pola **Krańcowa stopa procentowa** na **Krańcowa stopa procentowa przy przejściu** na stronie **Ustawienia księgi**. Jeśli ta opcja ma wartość **Nie**, stawka wynajmu głównego jest ustawiona na wartość pola **Stawka przyrostowego oprocentowania** na stronie **Szczegóły księgi**, niezależnie od typu przejścia w księdze.

4. Ustawienie **Zezwalaj na cofnięcia amortyzacji w zamkniętej księdze** na **Tak** umożliwia wycofanie transakcji wydatku amortyzacji. Transakcje wydatku można wycofywać nawet po zamknięciu wersji księgi.

    > [!NOTE]
    > Zaleca się, aby ta opcja była ustawiona na wartość **Nie**. Ustawienie tej opcji jest używane jako weryfikacja i kontrola, która zapobiega przypadkowemu zamortyzowaniu zamkniętej wersji księgi. Pozostawienie wartości **Nie** tej opcji pozwala utrzymać dokładną wartość księgową netto i przyszłych obliczeń amortyzacji.

5. Ustaw dla opcji **Zezwalaj na podział kwoty płatności** wartość **Tak** dlby umożliwić podział kwot płatności na skróconej karcie **wierszy harmonogramu płatności** na stronie **Dzierżawa**. Typy podziału płatności są definiowane w obszarze **Ustawienia** na stronie **Typy kwot płatności**. 

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
