---
title: Przepływ pracy obsługi dostawcy
description: Można zmodyfikować informacje o dostawcy, a następnie użyć przepływu pracy do ich zatwierdzenia.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: fb89b54b2f9377c216c447590a9434e3ff2d9bac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5248142"
---
# <a name="vendor-workflow"></a>Przepływ pracy obsługi dostawcy

[!include [banner](../includes/banner.md)]

Jeśli jest używany przepływ pracy obsługi dostawcy, zmiany wprowadzone w określonych polach są wysyłane do przepływu pracy w celu zatwierdzenia, zanim zostaną dodane do dostawcy.

## <a name="set-up-the-vendor-workflow"></a>Konfigurowanie przepływu pracy obsługi dostawcy

Aby korzystać z funkcji przepływu pracy, należy ją włączyć.

1. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Parametry modułu rozrachunków z dostawcami**.
2. Na karcie **Ogólne** na skróconej karcie **Zatwierdzenie dostawcy** dla opcji **Włącz zatwierdzanie dostawców** wybierz ustawienie **Tak**.
3. W polu **Zachowanie jednostki danych** wybierz zachowanie, które ma być używane podczas importowania danych:

    - **Zezwalaj na zmiany bez zatwierdzenia** — jednostka danych może aktualizować rekord dostawcy bez przetwarzania go za pomocą przepływu pracy.
    - **Odrzuć zmiany** — nie można wprowadzać zmian w rekordzie dostawcy. Import zakończy się niepowodzeniem dla pól objętych przepływem pracy.
    - **Utwórz propozycje zmian** — wszystkie pola zostaną zmodyfikowane, z wyjątkiem pól objętych przepływem pracy. Nowe wartości tych pól zostaną dodane do dostawcy jako proponowane zmiany, a przepływ pracy zostanie uruchomiony automatycznie.

4. Na liście pól dostawcy zaznacz pole wyboru **Włącz** dla każdego pola, które musi zostać zatwierdzone, zanim będzie można dokonać zmian.
5. Wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Przepływy pracy dla rozrachunków z dostawcami**.
6. Wybierz **Nowy**.
7. Zaznacz opcję **Przepływ pracy proponowanych zmian u dostawcy**. 
8. Skonfiguruj przepływ pracy, tak aby pasował do stosowanego procesu zatwierdzania. Zawarty w przepływie pracy element zatwierdzania **Zatwierdzenie proponowanej zmiany u dostawcy w przepływie pracy** spowoduje zastosowanie zmian do dostawcy.

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>Zmiana informacji o dostawcy i przesyłanie zmian do przepływu pracy

Po zmodyfikowaniu pola objętego przepływem pracy zostanie wyświetlona strona **Proponowane zmiany**. Na tej stronie jest wyświetlana oryginalna wartość pola oraz nowa wprowadzona przez Ciebie wartość. W zmodyfikowanym polu jest przywracana pierwotna wartość. Dodatkowo komunikat o stanie informuje, że zmiany nie został przesłane. 

Zawsze gdy modyfikujesz pole objęte przepływem pracy, jest ono dodawane do listy na stronie **Proponowane zmiany**. Aby odrzucić proponowaną wartość pola, należy użyć przycisku **Odrzuć** widocznego obok pola na liście. Aby odrzucić wszystkie zmiany, należy użyć przycisku **Odrzuć wszystkie zmiany** znajdującego się u dołu strony. Kliknij przycisk **OK**, aby zamknąć stronę.

Gdy istnieje co najmniej jedna proponowana zmiana, w okienku akcji pojawiają się dwie dodatkowe karty: **Proponowane zmiany** i **Przepływ pracy**.

1. Wybierz opcję **Proponowane zmiany**, aby otworzyć stronę **Proponowane zmiany** i przejrzeć zmiany.
2. Wybierz kolejno opcje **Przepływ pracy \> Prześlij**, aby przesłać zmiany do przepływu pracy.

    Stan na stronie został zmieniony na **Zmiany oczekują na zatwierdzenie**.

Przepływ pracy przebiega w sposób standardowy. Osoba zatwierdzająca jest kierowana na stronę **Dostawca**, gdzie może przejrzeć zmiany na stronie **Proponowane zmiany**, a następnie wybrać **Przepływ pracy \> Zatwierdź**, aby zatwierdzić przepływ pracy. Po wykonaniu wszystkich zatwierdzeń pola zostaną zaktualizowane za pomocą proponowanych przez Ciebie wartości.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]