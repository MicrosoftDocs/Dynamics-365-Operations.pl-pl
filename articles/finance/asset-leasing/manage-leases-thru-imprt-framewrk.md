---
title: Zarządzanie wynajmami za pośrednictwem struktury importu wynajmów
description: W tym temacie objaśniono sposób używania struktury importu wynajmów do jednoczesnego korygowania wielu umów wynajmu.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetLeaseLeaseImportHeader
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 083adf0a4bb74ac65e6f8b5077f65c74eb3fa337
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5880917"
---
# <a name="manage-leases-through-the-lease-import-framework"></a>Zarządzanie wynajmami za pośrednictwem struktury importu wynajmów

[!include [banner](../includes/banner.md)]

W tym temacie objaśniono sposób używania struktury importu wynajmów do korygowania wielu umów wynajmu w jednym kroku. Dzięki tej funkcji można zaoszczędzić czas i również zapewnić dokładniejsze korekty, zmniejszając ryzyko wystąpienia błędu człowieka. Ponadto ta funkcja może łączyć rozwiązanie Microsoft Dynamics 365 Finance z zewnętrznymi jednostkami danych w celu sprawnego przekazywania danych.

Poniższe jednostki danych mogą być używane do integrowania modułu Wynajem składnika majątku z zewnętrznymi systemami:

- Przejście wynajmu
- Przejście umowy dotyczącej płatności
- Przejście umowy wykonawczej

Proces importowania może być używany do korygowania wynajmu, aktualizowania informacji niefinansowych lub dodawania nowych umów wynajmu. Dane dotyczące wynajmu można przeglądać i edytować przed ich zaimportowaniem.

System może wykonywać następujące trzy procesy za pośrednictwem pakietu narzędzi importu wynajmu.

| Typ procesu  | opis |
|---------------|-------------|
| Dodaj rekord    | Zmigrowane umowy wynajmu mające ten typ procesu tworzą umowę wynajmu w systemie. Harmonogram płatności musi zostać potwierdzony ręcznie, a wpis w arkuszu dotyczący początkowego ujęcia musi zostać ręcznie zaksięgowany po zakończeniu migracji. |
| Aktualizuj rekord | Zmigrowane umowy wynajmu mające ten typ procesu aktualizują wartości pól dla umowy wynajmu już istniejącej w systemie. Aktualizowane są tylko pola zaznaczone na stronie **Aktualizuj wybór pól**. Zalecamy wybieranie pól niefinansowych na stronie **Aktualizuj wybór pól**, ponieważ ten typ procesu nie powoduje korygowania wynajmu. |
| Koryguj rekord | Zmigrowane umowy wynajmu mające ten typ procesu korygują umowę wynajmu. Ta korekta powoduje modyfikację umowy leasingu finansowego. Po przetworzeniu umowy wynajmu system tworzy nowy harmonogram płatności, korzystając z nowych danych otrzymanych z pakietu narzędzi importu wynajmu. System nie potwierdza harmonogramu płatności ani nie księguje wpisu w arkuszu korekty. |

Po przekazaniu informacji za pośrednictwem obszaru roboczego **Zarządzanie danymi** otwórz stronę **Nagłówek importu** (**Wynajem składnika majątku \> Struktura importu wynajmów \> Nagłówek importu**). Na tej stronie znajduje się lista wszystkich operacji importu trzech wymienionych wcześniej jednostek danych.

Aby wyświetlić dane pośrednie wynajmu przed uruchomieniem przetwarzania, wybierz opcję **Dane pośrednie**.

Funkcja porównania umożliwia porównanie importowanego rekordu z odpowiednim rekordem już znajdującym się w systemie. Aby porównać pojedynczy rekord wynajmu, wybierz umowę wynajmu, a następnie wybierz opcję **Porównaj**. Należy wykonać ten krok w celu wygenerowania raportu **Różnice** przed przeprowadzeniem migracji rekordów wynajmu. Funkcja Porównaj porównuje wartości w danych pośrednich z wartościami umów wynajmu, które obecnie znajdują się w systemie.

> [!NOTE]
> Funkcja Porównaj nie działa dla umów wynajmu o typie procesu **Dodaj rekord**, ponieważ nie ma nic do porównania z taką umową wynajmu.
>
> Aby jednocześnie porównać wiele umów wynajmu, wybierz kolejno opcje **Wynajem składnika majątku \> Struktura importu wynajmów \> Okresowe** i wybierz **Porównaj**.

Dla każdej jednostki można wyświetlić różnice między tym, co jest aktualnie w systemie, a tym, co się znajduje w tabelach przemieszczania. Dla każdej jednostki w tabelach przemieszczania kliknij opcję **Zobacz różnice**. Wyświetlone okno dialogowe zawiera wartość bieżącą i proponowaną wartość pośrednią.

Można także zaktualizować wartość pośrednią, zmieniając ją w kolumnie **Nowa wartość**, a następnie wybierając opcję **Aktualizuj przemieszczanie**.

Można sprawdzić poprawność umów wynajmu, aby upewnić się, że rekordy zostaną wprowadzone do systemu bez błędów. Przed rozpoczęciem migracji rekordu wynajmu system wykonuje kilka weryfikacji, aby umożliwić pomyślne zaimportowanie rekordu. Aby sprawdzić poprawność pojedynczej umowy wynajmu, wybierz pozycję **Weryfikuj**.

> [!NOTE]
> Aby jednocześnie sprawdzić poprawność wielu umów wynajmu, wybierz kolejno opcje **Wynajem składnika majątku \> Struktura importu wynajmów \> Okresowe** i wybierz **Weryfikuj**.

Aby przetworzyć pojedynczą umowę wynajmu, wybierz opcję **Migruj rekordy wynajmu** na stronie **Nagłówek importu**. Podczas migrowania umowy wynajmy system wykonuje akcję określoną w polu **Typ procesu**.

> [!NOTE]
> Aby jednocześnie dokonać migracji wielu umów wynajmu, wybierz kolejno opcje **Wynajem składnika majątku \> Struktura importu wynajmów \> Okresowe** i wybierz **Migracja**.

Po porównaniu umów wynajmu można uruchomić raport, aby wyświetlić różnice między wszystkimi umowami wynajmu objętymi daną operacją importu. Aby uruchomić raport dla jednej umowy wynajmu, zaznacz tę umowę w danych pośrednich, a następnie wybierz kolejno opcje **Porównaj i wyświetl raport \> Raport o różnicach**.

> [!NOTE]
> Aby jednocześnie porównać wiele umów wynajmu, wybierz kolejno opcje **Wynajem składnika majątku \> Struktura importu wynajmów \> Okresowe** i wybierz **Porównaj**. 

## <a name="set-up-update-fields"></a>Konfigurowanie aktualizowanych pól

Jeśli do aktualizacji umów wynajmu jest używana struktura importu wynajmów, a typ procesu to **Aktualizuj rekord**, można wybrać konkretne pola, które mają być aktualizowane.

1. Wybierz kolejno opcje **Wynajem składnika majątku \> Struktura importu wynajmów \> Ustawienia \> Aktualizuj wybór pól**.
2. Na wyświetlonej stronie wybierz pola, które mają zostać zaktualizowane, a następnie kliknij zieloną strzałkę, aby przenieść je do listy **Wybrane pola**. Tylko pola znajdujące się na liście **Wybrane pola** mogą być aktualizowane przy użyciu pakietu narzędzi importu wynajmu.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
