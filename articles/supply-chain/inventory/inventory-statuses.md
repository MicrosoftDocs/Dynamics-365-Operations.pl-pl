---
title: Stany zapasów
description: W tym artykule opisano, jak za pomocą stanów zapasów klasyfikować i śledzić zapasy.
author: yufeihuang
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db15ad94355823c699e83c9e3f47660f813e1c9a
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103470"
---
# <a name="inventory-statuses"></a>Stany zapasów

[!include [banner](../includes/banner.md)]

W tym artykule opisano, jak za pomocą stanów zapasów klasyfikować i śledzić zapasy.

## <a name="set-up-and-use-inventory-statuses"></a>Konfiguracja i używanie stanów zapasów

Stany zapasów służą do kategoryzowania zapasów. Można następnie zainicjować odpowiednie działania, takie jak uzupełnienie zapasów czy praca odłożenia.

Oto kilka przykładów zastosowania stanów zapasów:

- Tworzenie stanów zapasów dla dostępnych zapasów, transakcji przychodzących i wychodzących.
- Określanie domyślnego stanu zapasów dla transakcji magazynowych.
- Zmiana stanu zapasów dla towarów przed przyjęciem, podczas przyjęcia lub gdy są odłożone w ramach przesunięcia zapasów.
- Stan zapasów służy do wyceny towarów, gdy zostaną one zwrócone, i do planowania zapotrzebowania na towar podczas planowania głównego.

Stan zapasów jest jednym z wymiarów w grupie wymiarów magazynowania. Stany zapasów można sklasyfikować jako dostępne i niedostępne i można używać parametru **Blokowanie zapasów**, aby blokować towary z niedostępnym stanem zapasów. Pozycje ze stanem zablokowanym są uznawane za zapasy fizyczne i nie można ich użyć w zleceniu produkcyjnym, zamówieniu sprzedaży ani transakcji wychodzącej.

Można korzystać z pozycji magazynowych ze stanem niedostępne lub dostępne w przypadku pracy przychodzącej. Można na przykład utworzyć stan dostępny o nazwie *Gotowe*, stan niedostępny o nazwie *Uszkodzone* i stan zablokowany o nazwie *Zablokowane*. Podczas tworzenia zamówienia zakupu dla odebranych lub zwróconych towarów, jeśli wszystkie towary są uszkodzone, można zmienić stan zapasów tych towarów na *Uszkodzone* w wierszu zamówienia zakupu. Po przyjęciu tych towarów ich stan jest automatycznie ustawiany na *Zablokowane*. W przypadku zeskanowania uszkodzonych towarów za pomocą urządzenia przenośnego program Supply Chain Management może użyć dyrektywy lokalizacji i szablonów pracy, aby wyświetlać informacje o odpowiedniej lokalizacji lub zakresie lokalizacji, w których można odłożyć te towary. W przypadku zwróconych towarów na stronie *Transakcje magazynowe* tworzony jest typ **Rezerwacja**.

Można określić, które stany zapasów powodują blokowanie, za pomocą pól wyboru **Blokowania zapasów** na stronie **Stany zapasów**. Nie można używać stanów zapasów jako stanów blokowania dla zamówień sprzedaży, zleceń przeniesienia lub integracji projektów.

W przypadku pracy wychodzącej można użyć różnych stanów zapasów nieblokujących, aby kontrolować, dla których zapasów rezerwować. Jeśli masz towary ze stanem *Blokowanie* i zostało dla nich uruchomione planowanie główne, pozycje te zostaną uznane za brakujące, a zapasy są uzupełniane automatycznie. Ponadto w przypadku zleceń kontroli jakości związanych z pracą wychodzącą nie można zaktualizować **Stanu zapasów** w ramach sprawdzania poprawności zlecenia kontroli jakości.

> [!NOTE]
> Nie możesz zmienić stanu zapasów w lokalizacjach, w których istnieje otwarta praca. Na przykład, jeśli dokonałeś zakupu dla towaru, ale nie wykonałeś kroku odkładania, to dla lokalizacji odbioru istniałaby otwarta praca i wystąpiłby błąd, gdybyś próbował zmienić stan zapasów w tej lokalizacji. Ukończenie lub anulowanie powiązanych prac pozwoliłoby na zmianę statusu.
>
> Zwykle status dostępnych zapasów związanych z otwartymi pracami magazynowymi zmieniają tylko pracownicy korzystający z aplikacji mobilnej Warehouse Management, np. podczas wykonywania procesu przemieszczania.

Po skonfigurowaniu stanów zapasów można ustawić domyślny stan zapasów dla oddziału, towaru i magazynu. Można również ustawić domyślny stan dla zamówień sprzedaży, przeniesienia i zakupu. Domyślny stan dla zamówień sprzedaży i wychodzących zamówień przeniesienia opcja **Blokowanie towarów** nie może mieć wartości *Tak*. Stan zapasów przejmowany z domyślnych ustawień lokalizacji, magazynu, towaru, zamówienia zakupu, zamówienia przeniesienia czy zamówienia sprzedaży może zostać zmieniony za pomocą urządzenia przenośnego lub w wierszu zamówienia zakupu, zamówienia sprzedaży lub zamówienia przeniesienia.

Aby zaplanować zapotrzebowanie na towary z dostępnym stanem zapasów, należy wybrać opcję **Plan zapotrzebowania wg wymiaru** dla wymiaru magazynowego na stronie **Grupy wymiarów magazynowania**. Po otwarciu **Kreatora zapotrzebowania na towar** towary z dostępnym stanem pojawiają się na stronie **Stan**. Do tworzenia ustawień zapotrzebowania dla tych pozycji wybierz identyfikator stanu zapasów dla dostępnych zapasów. Zgodnie z ustawieniami zapotrzebowania, można obliczać zapotrzebowania na pozycje i prognozować dostawy oraz popyt na dostępne towary podczas planowania głównego. Nie można utworzyć ustawienia zapotrzebowania na towary ze stanem zablokowanym. Alternatywnie można użyć strony **Zapotrzebowanie na towar**, aby utworzyć lub zmodyfikować parametry zapotrzebowania na towar.

## <a name="change-inventory-statuses"></a>Zmiana stanów zapasów

Stany zapasów można zmieniać przy użyciu strony **Dostępne zapasy według lokalizacji** lub za pomocą zadania okresowego *Zmiana stanu zapasów*.

- Podczas korzystania z zadania okresowego *Zmiana stanu zapasów* można wybrać rekordy, które mają zostać uwzględnione, i określić, że zadanie ma być uruchamiane w partii w wybranym interwale.
- Aby zmienić stan zapasów jako proces ad hoc, przejdź na stronę **Dostępne zapasy według lokalizacji**, wybierz odpowiednie rekordy, a następnie wybierz przycisk **Zmiana stanu zapasów**.

> [!NOTE]
> Funkcja *zmiany stanu zapasów towarów kontrolowanych przez wymiary śledzenia* umożliwia zmianę stanu zapasów towarów kontrolowanych przez wymiary śledzenia, w tym również aktualizację tylko wybranych rekordów. Od wersji 10.0.25 Supply Chain Management ta funkcja jest obowiązkowa i nie można jej wyłączyć. Jeśli używasz wersji starszej niż 10.0.25, administratorzy mogą włączyć lub wyłączyć tę funkcję, wyszukując funkcję *Zmień stan zapasów towarów kontrolowanych przez wymiary śledzenia* w obszarze roboczym [Zarządzanie funkcjami](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Jeśli funkcja jest włączona, można wykonywać następujące działania:
>
> - Na stronie **Dostępne zapasy według lokalizacji** można grupować wiersze na podstawie wyświetlonych wymiarów, korzystając z przycisku **Wyświetl wymiary**, i zmieniać stan w wybranych wierszach.
> - Na stronie **Dostępne zapasy według lokalizacji** można wybrać wiele rekordów, a następnie za pomocą przycisku **Zmiana stanu zapasów** zmienić wszystkie te rekordy jednocześnie.
> - W przypadku zadania okresowego **Zmiana stanu zapasów** użytkownik może filtrować wiersze według wymiarów śledzenia.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
