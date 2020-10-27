---
title: Przepływ pracy odbiorcy
description: Ten temat zawiera informacje dotyczące przepływu pracy odbiorcy. Możesz zmienić określone pola dla odbiorcy, a następnie wysłać te zmiany do zatwierdzenia, używając przepływu pracy, zanim zostaną one dodane do danych odbiorcy.
author: mikefalkner
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: cb8519db2f5d52d4e317b485d6ecc910956788cb
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2020
ms.locfileid: "3975323"
---
# <a name="customer-workflow"></a>Przepływ pracy odbiorcy

[!include [banner](../includes/banner.md)]

Przepływ pracy odbiorcy został dodany do wersji 8.0.4. Możesz zmienić określone pola dla odbiorcy, a następnie wysłać te zmiany do zatwierdzenia, używając przepływu pracy, zanim zostaną one dodane do danych odbiorcy.

## <a name="set-up-the-customer-workflow"></a>Konfigurowanie przepływu pracy odbiorcy

Aby móc używać funkcji przepływu pracy odbiorcy, musisz ją włączyć.

1. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Parametry modułu rozrachunków z odbiorcami**.
2. Na karcie **Ogólne** na skróconej karcie **Zatwierdzenie odbiorcy** ustaw dla opcji **Włącz zatwierdzanie odbiorców** wartość **Tak**, aby włączyć tę funkcję.
3. W polu **Zachowanie jednostki danych** wybierz zachowanie, którego jednostka danych ma używać podczas importowania danych:

    - **Zezwalaj na zmiany bez zatwierdzenia** — jednostka może zaktualizować rekord odbiorcy bez konieczności przetwarzania go w przepływie pracy.
    - **Odrzuć zmiany** — Nie można wprowadzić zmian w rekordzie odbiorcy. Import zakończy się niepowodzeniem w przypadku pól, które są skonfigurowane do użycia w przepływie pracy.
    - **Utwórz propozycje zmian** — Wszystkie pola zostaną zmienione, z wyjątkiem pól, które są skonfigurowane do użycia w przepływie pracy. Nowe wartości tych pól zostaną dodane do odbiorcy jako proponowane zmiany, a przepływ pracy zostanie uruchomiony automatycznie.

4. Następnie na liście pól odbiorcy zaznacz pole wyboru **Włącz** dla każdego pola, które musi zostać zatwierdzone, zanim będzie można wprowadzić w nim zmianę.
5. Wybierz kolejno pozycje **Rozrachunki z odbiorcami \> Ustawienia \> Przepływy pracy dla rozrachunków z odbiorcami**.
6. Wybierz pozycję **Nowy**.
7. Wybierz pozycję **Przepływ pracy proponowanej zmiany u odbiorcy**. 
8. Skonfiguruj przepływ pracy, tak aby pasował do Twojego procesu zatwierdzania. Element zatwierdzania przepływu pracy **Zatwierdzenie proponowanej zmiany u odbiorcy w przepływie pracy** zastosuje zmiany do danych odbiorcy.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Zmienianie informacji dotyczących odbiorcy i przesyłanie zmian do przepływu pracy

Jeśli zmienisz pole, które jest skonfigurowane do użycia w przepływie pracy, zostanie wyświetlona strona **Proponowane zmiany**. Na tej stronie jest wyświetlana oryginalna wartość pola oraz nowa wprowadzona przez Ciebie wartość. Przywracana jest oryginalna wartość zmienionego przez Ciebie pola. Komunikat o stanie na stronie informuje, że Twoje zmiany nie zostały przesłane.

Zawsze, gdy zmienisz pole, które jest skonfigurowane do użycia w przepływie pracy, to pole jest dodawane do listy proponowanych zmian. Aby odrzucić proponowaną wartość pola, użyj przycisku **Odrzuć**, który znajduje się obok pola na liście. Aby odrzucić wszystkie zmiany, użyj przycisku **Odrzuć wszystkie zmiany**, który znajduje się u dołu strony. Wybierz przycisk **OK**, aby zamknąć stronę.

Jeśli będzie dostępna co najmniej jedna proponowana zmiana, w okienku akcji zostaną wyświetlone dwa dodatkowe menu: **Proponowane zmiany** i **Przepływ pracy**.

1. Wybierz pozycję **Proponowane zmiany**, aby otworzyć stronę **Proponowane zmiany** i przejrzeć swoje zmiany.
2. Wybierz kolejno pozycje **Przepływ pracy \> Prześlij**, aby przesłać zmiany do przepływu pracy.

    Status na stronie zmienia się na **Zmiany oczekują na zatwierdzenie**.

Przepływ pracy jest zgodny ze standardowym procesem przepływu pracy w aplikacji. Osoba zatwierdzająca jest kierowana na stronę **Odbiorca**, gdzie może przejrzeć zmiany na stronie **Proponowane zmiany**, a następnie wybrać **Przepływ pracy \> Zatwierdź**, aby zatwierdzić przepływ pracy. Po wykonaniu wszystkich zatwierdzeń pola zostaną zaktualizowane za pomocą proponowanych przez Ciebie wartości.
