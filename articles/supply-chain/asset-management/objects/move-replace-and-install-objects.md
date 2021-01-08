---
title: Przenoszenie, zamiana i instalowanie składników majątku
description: W tym temacie opisano sposób przenoszenia, zastępowania i instalowania składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectReplace, EntAssetObjectInstallLookup, EntAssetObjectMove, EntAssetObjectTableEditSubObjects
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec150adb35eb0600844245b14cbec9e9632ab337
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4435280"
---
# <a name="move-replace-and-install-assets"></a>Przenoszenie, zamiana i instalowanie składników majątku

[!include [banner](../../includes/banner.md)]

 

W tym temacie opisano sposób przenoszenia, zastępowania i instalowania składników majątku w module Zarządzanie składnikami majątku. Można utworzyć poszczególne składniki majątku, które nie mają relacji z innymi składnikami majątku, lub utworzyć strukturę składników majątku zawierającą składnik majątku najwyższego poziomu (nadrzędny) i powiązane podrzędne składniki majątku. W module Zarządzaniu składnikami majątku istnieją trzy podejścia do przenoszenia i zmieniania lokalizacji składnika majątku:

- **Przenieś** – przenieś składnik majątku do innej struktury składników majątku lub do innej lokalizacji w tej samej strukturze składników majątku.
- **Zamień** — tymczasowo usuń składnik majątku ze struktury składników majątku, aby można ją było naprawić lub odnowić, a następnie dodaj odnowiony składnik majątku do struktury składników majątku później. Alternatywnie można trwale zastąpić używany składnik majątku nowym składnikiem majątku.
- **Zainstaluj** — zainstaluj nadrzędny składnik majątku i wszelkie pokrewne podrzędne składniki majątku w lokalizacji czynności konserwacyjnych.

> [!NOTE]
> Składnik majątku, który jest przenoszony, zastępowany lub instalowany, musi być związane z inną lokalizacją czynności konserwacyjnych. W takim przypadku składnik majątku może używać wymiarów finansowych lokalizacji czynności konserwacyjnych. Na stronie **Typy lokalizacji czynności konserwacyjnych** można skonfigurować obsługę wymiarów finansowych w lokalizacjach czynności konserwacyjnych.

## <a name="move-asset"></a>Przenieś składnik majątku

Użyj funkcji **Przenieś składnik majątku**, aby przenieść składnik majątku do innej struktury składników majątku lub do innej lokalizacji w tej samej strukturze składników majątku. Można również przenieść składnik majątku poza strukturę składników majątku, tak aby stał się autonomicznym składnikiem majątku, który nie ma relacji struktury.

> [!NOTE]
> Nie należy używać tej funkcji, jeśli aktywa są naprawiane lub tymczasowo wymieniane. Zamiast tego należy użyć funkcji **Zastąp składnik majątku**, która jest opisany w dalszej części tego tematu.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku** lub **Aktywne składniki majątku**.
2. Na liście zaznacz grupę składników majątku do przeniesienia. Jeśli składnik majątku ma składniki podrzędne, możesz również przenieść te składniki majątku.
3. Wybierz **Przenieś składnik majątku**.
4. Aby przenieść składnik majątku w taki sposób, żeby stał się częścią struktury składników majątku, wybierz nowy składnik majątku nadrzędny w polu **Nadrzędny składnik majątku**. Jeśli przenosisz podrzędny składnik majątku i chcesz uczynić go autonomicznym składnikiem majątku, który nie relacji z żadną strukturą, zostaw pole **Nadrzędny składnik majątku** puste.
5. Domyślnie pole **Data wprowadzenia** jest ustawione na bieżącą datę i godzinę. Można jednak wybrać inną datę i godzinę, od której obowiązuje przeniesienie danego składnika majątku.
6. Kliknij przycisk **OK**.

## <a name="replace-asset"></a>Zamień składnik majątku

Użyj funkcji **Zamień składnik majątku** w odniesieniu do naprawiania, odnawiania lub trwałe zastąpienia zużytego składnika majątku przez nowy składnik majątku. Ta funkcja służy do zastępowania podrzędnych składników majątku w strukturze składników majątku. W przypadku nadrzędnych składników majątku (tj. składników majątku, które nie mają obecnie nadrzędnego składnika majątku), ta zamiana jest dokonywana w lokalizacja czynności konserwacyjnych. Aby uzyskać więcej informacji na temat zastępowania zasobów nadrzędnych w lokalizacji czynności konserwacyjnych, zobacz temat [Instalowanie zasobów w lokalizacjach czynności konserwacyjnych](../functional-locations/install-objects-on-functional-locations.md).

> [!NOTE]
> Jeśli warsztat jest powiązany z działem produkcyjnym, można utworzyć lokalizacje czynności konserwacyjnych, takie jak **Naprawy**, **Złomowanie** i **Magazyn** do obsługi naprawy i zamiany składników majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku** lub **Aktywne składniki majątku**.
2. Na liście zaznacz podrzędny składnik majątku, który chcesz zamienić. Jeśli składnik majątku ma składniki podrzędne, możesz również zamienić te składniki majątku.
3. Wybierz **Zamień składnik majątku**.

    Pole **Zmiana struktury** pokazuje ostatnią datę i godzinę przeniesienia wybranego składnika majątku i powiązanych składników podrzędnych do struktury składników majątku.

4. W sekcji **Wybrane składniki majątku** w polu **Docelowa lokalizacja czynności konserwacyjnych** wybierz lokalizację czynności konserwacyjnych, do której chcesz przenieść składnik majątku. Na przykład wybierz lokalizację **Naprawy** lub **Złomowanie**.

    W sekcji **Nadrzędny składnik majątku** pole **Data wprowadzenia** pokazuje ostatnią datę i godzinę zainstalowania lub przeniesienia składnika nadrzędnego i powiązanych składników majątku na bieżącą lokalizację czynności konserwacyjnych.

5. W sekcji **Nowy składnik majątku** w polu **Składnik majątku** wybierz składnik majątku do wstawienia jako tymczasowy lub trwały zamiennik wybranego składnika majątku. Ten składnik majątku może obecnie znajdować się w innej lokalizacji czynności konserwacyjnych, takiej jak **Magazyn**.
7. W sekcji **Obowiązuje od** pole **Data wprowadzenia** jest domyślnie ustawione na bieżącą datę i godzinę. Można jednak wybrać inną datę i godzinę, od której obowiązuje zamiana danego składnika majątku.
8. Kliknij przycisk **OK**.

## <a name="install-asset"></a>Zainstaluj składnik majątku.

Użyj funkcji **Zainstaluj składnik majątku**, aby zainstalować strukturę składników majątku w lokalizacji czynności konserwacyjnych.

> [!NOTE]
> Zawsze wybieraj nadrzędny składnik majątku. Nadrzędny składnik majątku i powiązane składniki podrzędne zostaną przeniesione do wybranej lokalizacji czynności konserwacyjnych.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Wszystkie składniki majątku** lub **Aktywne składniki majątku**.
2. Na liście wybierz nadrzędny składnik majątku do zainstalowania w innej lokalizacji czynności konserwacyjnych.
3. Wybierz opcję **Zainstaluj składnik majątku**.

    Sekcja **Atrybuty** pokazuje atrybuty składnika majątku, które zostaną skonfigurowane na nadrzędnym składniku majątku.

4. W polu **Lokalizacja czynności konserwacyjnych** wybierz nową lokalizację.
5. Domyślnie pole **Data wprowadzenia** jest ustawione na bieżącą datę i godzinę. Można jednak wybrać inną datę i godzinę, od której obowiązuje dana instalacja w strukturze składników majątku.
6. Kliknij przycisk **OK**.
