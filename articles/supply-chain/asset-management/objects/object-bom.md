---
title: Obiekty BOM składnika majątku
description: W tym artykule opisano BOM składników majątku w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetStandardSparePartsItemGroup, EntAssetObjectBOM
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 71b861ec31e704e001aab29245b9e24ce8beb0de
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882787"
---
# <a name="asset-boms"></a>Obiekty BOM składnika majątku

[!include [banner](../../includes/banner.md)]

 

W tym artykule opisano BOM składników majątku w module Zarządzanie składnikami majątku. Strona **BOM składnika majątku** zawiera listę wszystkich elementów (części zamiennych i innych pozycji) używanych w składniku majątku w całym jego cyklu życia. Podczas tworzenia nowego składnika majątku należy rozważyć skonfigurowanie BOM składnika majątku w ramach procedury instalacji. W ten sposób można śledzić historię elementów dla składnika majątku od daty utworzenia.

Po zakończeniu zadania konserwacji i zarejestrowaniu zużycia pozycji w zleceniu pracy, można śledzić zużycie części zamiennych i innych elementów, które są używane w składniku majątku. Ta funkcja pozwala zachować pełny rekord konsumpcji wszystkich składników majątku. Można na przykład użyć rekordu do monitorowania, czy dana część zamienna jest często zastępowana, czy też do śledzenia części zamiennych lub innych elementów, które są aktualnie używane na danym składnikiem majątku.

> [!NOTE]
> W przypadku zlecenia roboczego zużycie pozycji może obejmować zarówno części zamienne, jak i inne, dodatkowe elementy, takie jak smary, sworznie i uszczelki.

BOM składnika majątku może być automatycznie aktualizowany na podstawie ustawień w module Zarządzanie składnikami majątku. Jeśli stan cyklu życia zlecenia pracy został utworzony w celu obsługi gotowych lub zakończonych zleceń pracy, a opcja **Aktualizuj BOM składnika majątku** dla tego stanu cyklu życia zlecenia pracy jest ustawiona na **Tak** na stronie **Stany cyklu życia zlecenia pracy**, wszystkie elementy, które są używane w zleceniu pracy zostaną automatycznie zaktualizowane na stronie **BOM składnika majątku** po zaktualizowaniu zlecenia pracy do tego stanu cyklu życia. 


Można również ręcznie zaktualizować BOM składnika majątku, tworząc nowe wiersze pozycji na stronie **BOM składnika majątku**.

Na stronie **BOM składnika majątku** można śledzić historię części zamiennych dla składników majątku po zarejestrowaniu zużycia pozycji w zleceniu pracy. Aby korzystać z tej funkcji, należy wybrać grupy elementów, które mają być używane do rejestracji części zamiennych na stronie **Grupy pozycji części zamiennych**.

Aby korzystać z funkcji BOM składnika majątku, należy najpierw skonfigurować wymagane grupy pozycji części zamiennych. Następnie jeśli BOM składnika majątku ma być automatycznie aktualizowany po zakończeniu zlecenia pracy, można skonfigurować stan cyklu życia zlecenia pracy do obsługi tej aktualizacji. 


## <a name="set-up-spare-parts-item-groups"></a>Konfigurowanie grup pozycji części zamiennych

Konfiguracja historii części zamiennych jest oparta na grupach pozycji utworzonych w module **Zarządzanie składnikami majątku i magazynem**. W module Zarządzanie składnikami majątku można skonfigurować grupy pozycji, aby można było śledzić historię części zamiennych dla pozycji w wybranych grupach pozycji.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Składnik majątku** \> **Grupy pozycji części zamiennych**.
2. Wybierz opcję **Nowa**, aby skonfigurować grupę pozycji.
3. W polu **Grupa pozycji** wybierz grupę. Nazwa grupy jest automatycznie wprowadzana w polu **Nazwa**.

## <a name="view-and-update-asset-boms"></a>Wyświetlanie i aktualizowanie obiektów BOM składnika majątku

Po zaksięgować zużycia pozycji w zleceniu pracy, można wyświetlić zużycie zarejestrowanej pozycji na stronie **BOM składnika majątku**.

1. Wybierz **Zarządzanie składnikami majątku** \> **Wspólne** \> **Składniki majątku** \> **Aktywne składniki majątku**. Wybierz składnik majątku na liście, a następnie wybierz pozycję **BOM składnika majątku**.

    > [!NOTE]
    > Aby wyświetlić wszystkie rejestracje zużycia składnika majątku dla wszystkich składników majątku, wybierz **Zarządzanie składnikami majątku** \> **Informacje** \> **Składniki majątku** \> **BOM składnika majątku**.

2. Wybierz pozycję **Aktualizuj BOM składnika majątku**. Można dodawać składniki majątku, typy składników majątku oraz składniki majątku do aktualizacji zgodnie z wymaganiem, wybierając opcję **Zaznacz**. Wybierz przycisk **OK**, aby rozpocząć aktualizację. Można również skonfigurować funkcję aktualizacji jako zadanie wsadowe.
3. Jeśli chcesz zobaczyć więcej informacji związanych z pozycjami, możesz dodać wymiary magazynowe. Wybierz **Zapasy** \> **Wyświetlanie wymiarów**, a następnie zaznacz pola wyboru odpowiadające wymiarom, które chcesz zobaczyć. Aby zachować tę konfigurację dla wszystkich składników majątku na stronie **BOM składnika majątku**, ustaw opcję **Zapisz konfigurację** na **Tak**.
4. Aby uzyskać informacje o tym, gdzie w module Zarządzaniu składnikami majątku jest używany element w wybranym wierszu, w odniesieniu do składników majątku domyślnych typów zadań, części zamiennych i zleceń pracy, wybierz opcję **Używająca pozycja**. 
5. Jeśli chcesz zobaczyć tylko aktywne linie towaru, wybierz kolejno **Wyświetl** \> **Bieżące**. Aby zobaczyć wszystkie wiersze pozycji, w tym wiersze, w których data wygaśnięcia jest wcześniejsza niż data bieżąca, zaznacz **Wyświetl** \> **Wszystkie**.

> [!NOTE]
> Po zakończeniu zlecenia pracy, jeśli niektóre pozycje lub części zamienne związane z powiązanym składnikiem majątku wygasły lub zostały zastąpione innymi pozycjami lub częściami zamiennymi, zaleca się odpowiednie zaktualizowanie BOM składnika majątku.

## <a name="create-a-new-item-line-in-an-asset-bom"></a>Tworzenie nowego wiersza w obiekcie BOM składnika majątku

Można ręcznie tworzyć wiersze pozycji dla składników majątku.

1. Na stronie **BOM składnika majątku** wybierz opcję **Nowe**.
2. W polu **Składnik majątku** wybierz składnik majątku, dla którego ma zostać dodany wiersz pozycji.
3. W polu **Numer wiersza** wprowadź numer kolejnego wiersza.
4. W polu **Data wejścia w życie** wprowadź datę początkową dla składnika majątku.
5. Jeśli element wygaśnie, w polu **Wygaśnięcie** wprowadź datę końcową.
6. W polu **Numer pozycji** wybierz pozycję. Nazwa jest automatycznie wprowadzana w polu **Nazwa produktu**.
7. W polu **Ilość** wprowadź używaną ilość. Pole **Jednostka** jest aktualizowane automatycznie.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]