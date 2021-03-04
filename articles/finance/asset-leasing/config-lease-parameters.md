---
title: Konfigurowanie parametrów wynajmu (wersja zapoznawcza)
description: W tym temacie opisano ustawienia konfiguracji dotyczące wynajmu składników aktywów, takie jak informacje o zabezpieczeniach i ustawienia księgowania.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TaxTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f71006570cd8f2bdc0385388eae0800cd29d3ec8
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/28/2020
ms.locfileid: "4447000"
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

4. Ustawienie **Zezwalaj na cofnięcia amortyzacji w zamkniętej wersji księgi** na **Tak** umożliwia wycofanie transakcji wydatku amortyzacji. Transakcje wydatku można wycofywać nawet po zamknięciu wersji księgi.

    > [!NOTE]
    > Zaleca się, aby ta opcja była ustawiona na wartość **Nie**. Ustawienie tej opcji jest używane jako weryfikacja i kontrola, która zapobiega przypadkowemu zamortyzowaniu zamkniętej wersji księgi. Pozostawienie wartości **Nie** tej opcji pozwala utrzymać dokładną wartość księgową netto i przyszłych obliczeń amortyzacji.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]