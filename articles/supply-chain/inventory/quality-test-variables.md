---
title: Zmienne testowe zarządzania jakością
description: W tym temacie opisano sposób tworzenia zmiennych testowych, których można używać w testach jakościowych w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.
author: yufeihuang
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yufeihuang
ms.search.validFrom: 2020-06-17
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4495c3d3f8df9f07ec079d8e497a17979abbe3ee
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7575879"
---
# <a name="quality-management-test-variables"></a>Zmienne testowe zarządzania jakością

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób tworzenia zmiennych testowych, których można używać w testach jakościowych w zleceniach kontroli jakości w systemie Microsoft Dynamics 365 Supply Chain Management.

W każdym teście jakościowym zdefiniowanym na stronie **Testy** musisz zdefiniować zmienną testową i możliwe wyniki. (Dla testów jakościowych w polu **Typ** na stronie **Testy** ustawiono wartość *Opcja*).

Strona **Zmienne testowe** służy do konfigurowania, edytowania i wyświetlania możliwych wyników zmiennej testowej skojarzonej z testem jakościowym. Dla każdego wyniku przypisuje się stan wyniku *Zaliczony* lub *Niezaliczony*, aby określić, czy test został zaliczony czy niezaliczony, gdy ten wynik zostanie wybrany jako wynik testu. Strona **Grupy testów** służy do przypisywania zmiennej testowej i domyślnego wyniku do konkretnego testu.

Zaleca się, aby dla każdej zmiennej testowej zdefiniować co najmniej dwa wyniki: jeden ze stanem wyniku *Zaliczony*, a drugi ze stanem wyniku *Niezaliczony*. Nie ma ograniczeń co do łącznej liczby zmiennych lub wyników, które można zdefiniować. Ponadto wiele testów może używać tych samych zmiennych testowych do rejestrowania wyników.

## <a name="examples-of-test-variables"></a>Przykłady zmiennych testowych

### <a name="example-1"></a>Przykład 1

Firma produkcyjna wykonuje dwa testy na wyprodukowanych materiałach. W jednym teście poziom pH jest skojarzony z kolorowym paskiem testowym. Dopuszczalne poziomy pH to jaśniejsze kolory, a nieakceptowalne poziomy pH mają ciemniejsze kolory. W innym teście jest wykonywanych wiele inspekcji wzrokowych, a pracownicy jakości według własnego uznania stwierdzają, czy towar przechodzi kontrolę wizualną czy nie.

### <a name="example-2"></a>Przykład 2

Firma produkująca ciasteczka przeprowadza testy kontrolne na gotowym produkcie. Ten test inspekcji zawiera kilka zmiennych. Jedną ze zmiennych jest smak, a jej możliwe wyniki to dobry i zły. Druga zmienna to kolor z wynikami zbyt ciemny, zbyt jasny i prawidłowy.

## <a name="create-a-test-variable"></a>Tworzenie zmiennej testowej

Aby utworzyć zmienną testową, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Ustawienia \> Kontrola jakości \> Zmienne testowe**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Zmienna** — umożliwia wprowadzenie unikatowego identyfikatora lub nazwy zmiennej.
    - **Opis** – wprowadź szczegółowy opis zmiennej.

1. Gdy nowy wiersz jest nadal zaznaczony, wybierz opcję **Wyniki** w okienku akcji.
1. Na stronie **Wyniki zmiennych testowych** w okienku akcja wybierz pozycję **Nowa**, aby dodać wiersz do siatki. Następnie ustaw następujące pola dla nowego wiersza:

    - **Wynik** — umożliwia wprowadzenie unikatowego identyfikatora lub nazwy wyniku.
    - **Opis** – wprowadź szczegółowy opis wyniku.
    - **Stan wyniku** — Dla każdego wyniku przypisuje się stan wyniku *Zaliczony* lub *Niezaliczony*, aby określić, czy test został zaliczony czy niezaliczony, gdy ten wynik zostanie wybrany jako wynik testu.

1. Powtórz poprzedni krok dla każdego dodatkowego wyniku. Upewnij się, że co najmniej jeden wynik ma stan wyniku *Zaliczony* i co najmniej jeden ma stan wyniku *Niezaliczony*.
1. Zamknij strony.

## <a name="additional-resources"></a>Dodatkowe zasoby

- [Przyrządy testowe zarządzania jakością](quality-test-instruments.md)
- [Testy zarządzania jakością](quality-tests.md)
- [Grupy testowe zarządzania jakością](quality-test-groups.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
