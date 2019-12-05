---
title: Typy lokalizacji czynności konserwacyjnych
description: W tym temacie opisano sposób tworzenia typów lokalizacjach czynności konserwacyjnych w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0468cb0b1717b7cf0ccb391da09a4e7d788124f3
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812221"
---
# <a name="functional-location-types"></a>Typy lokalizacji czynności konserwacyjnych

[!include [banner](../../includes/banner.md)]

 

W tym temacie opisano sposób tworzenia typów lokalizacjach czynności konserwacyjnych w module Zarządzanie składnikami majątku. Typy lokalizacji czynności konserwacyjnych są używane do zarządzania wymaganiami dla lokalizacji czynności konserwacyjnych, w tym w jaki sposób składniki majątku są instalowane w lokalizacji czynności konserwacyjnych. Można skonfigurować typy składników majątku, plany konserwacji, atrybuty lokalizacji czynności konserwacyjnych oraz wymagania dotyczące atrybutów składnika majątku, które mają być używane w lokalizacji czynności konserwacyjnych używającej określonego typu lokalizacji czynności konserwacyjnych. Gdy tworzysz lokalizację czynności konserwacyjnych, typ lokalizacji czynności konserwacyjnych jest obowiązkowy.

>[!NOTE] 
>Aby można było pracować z lokalizacjami czynności konserwacyjnych, należy utworzyć domyślną lokalizację czynności konserwacyjnych, która będzie używana tylko w celu tworzenia nowych składników majątku. Dla tej domyślnej lokalizacji czynności konserwacyjnych należy utworzyć domyślny typ lokalizacji czynności konserwacyjnych, który jest bardzo prosty i umożliwia zainstalowanie wielu składników majątku w domyślnej lokalizacji czynności konserwacyjnych. Zobacz [Tworzenie lokalizacji czynności konserwacyjnych](../functional-locations/create-functional-locations.md), aby uzyskać więcej informacji na temat konfigurowania lokalizacji czynności konserwacyjnych.

## <a name="create-a-default-functional-location-type"></a>Tworzenie domyślnego typu lokalizacji czynności konserwacyjnych

W tej procedurze pokazano, jak utworzyć domyślny typ lokalizacji czynności konserwacyjnych, który ma być używany dla domyślnej lokalizacji czynności konserwacyjnych.

1. Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Lokalizacje czynności konserwacyjnych** > **Typy lokalizacji czynności konserwacyjnych**.
2. Wybierz opcję **Nowy**, aby utworzyć nowy typ lokalizacji czynności konserwacyjnych.
3. Wstaw identyfikator typu lokalizacji czynności konserwacyjnych w polu **Typ lokalizacji czynności konserwacyjnych**, na przykład „domyślna”, oraz nazwę w polu **Nazwa**.
4. Wybierz model cyklu życia w polu **Model cyklu życia lokalizacji czynności konserwacyjnych**.
5. Wybierz opcję „Tak” na przełączniku **Wiele zasobów**, aby zezwolić na zainstalowanie większej liczby składników majątku w lokalizacji czynności konserwacyjnych (domyślna lokalizacja czynności konserwacyjnych) przy użyciu tego typu.

Tworzony jest typ lokalizacji czynności konserwacyjnych, który ma być używany tylko dla domyślnej lokalizacji czynności konserwacyjnych. Nie należy dodawać żadnych dodatkowych wymagań ani ograniczeń do tego domyślnego typu lokalizacji czynności konserwacyjnych.


## <a name="create-functional-location-types"></a>Tworzenie typów lokalizacji czynności konserwacyjnych

1. Wybierz **Zarządzanie składnikami majątku** > **Ustawienia** > **Lokalizacje czynności konserwacyjnych** > **Typy lokalizacji czynności konserwacyjnych**.
2. Wybierz opcję **Nowy**, aby utworzyć nowy typ lokalizacji czynności konserwacyjnych.
3. Wstaw identyfikator typu lokalizacji czynności konserwacyjnych w polu **Typ lokalizacji czynności konserwacyjnych** oraz nazwę w polu **Nazwa**.
4. Wybierz model cyklu życia w polu **Model cyklu życia lokalizacji czynności konserwacyjnych**. Więcej informacji na temat stanów i modeli cyklu życia lokalizacji czynności konserwacyjnych, zobacz temat [Stany cyklu życia lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-stages.md).
5. Wybierz opcję „Tak” na przełączniku **Wiele zasobów**, jeśli powinna być dostępna możliwość zainstalowania kilku składników majątku w lokalizacji czynności konserwacyjnych przy użyciu tego typu lokalizacji czynności konserwacyjnych. W przypadku wybrania opcji „Nie” można zainstalować tylko *jeden* składnik majątku w lokalizacji czynności konserwacyjnych przy użyciu tego typu lokalizacji czynności konserwacyjnych.
6. Wybierz „Tak” na przełączniku **Aktualizuj wymiar składnika majątku**, jeśli chcesz, aby składniki majątku zainstalowane w lokalizacji czynności konserwacyjnych tego typu automatycznie używały wymiarów finansowych związanych z lokalizacją czynności konserwacyjnych. Oznacza to, że jeśli zmienisz wymiary finansowe w formularzu [Tworzenie lokalizacji czynności konserwacyjnych](../functional-locations/create-functional-locations.md), a lokalizacja czynności konserwacyjnych używa typu lokalizacji czynności konserwacyjnych z tym przełącznikiem ustawionym na „Tak”, wymiary finansowe są automatycznie aktualizowane na wszystkich składnikach majątku zainstalowanych w tej lokalizacji czynności konserwacyjnych.
7. Pole **Typ składnika majątku** jest używane, jeśli chcesz automatycznie utworzyć *jeden* składnik majątku dla lokalizacji czynności konserwacyjnych o tym samym identyfikatorze i nazwie co tworzona lokalizacja czynności konserwacyjnych. Może to być na przykład istotne w przypadku utworzenia statycznej lokalizacji czynności konserwacyjnych, takiej jak budynek lub proces. W takim przypadku wybierz typ składnika majątku, który ma być używany dla automatycznie utworzonego składnika majątku. Pamiętaj, że jeśli dokonujesz wyboru w tym polu, przełącznik **Wiele składników majątku** musi być ustawiony na „Nie”.
8. Na skróconej karcie **Typy składników majątku** wybierz typy składników majątku, które powinny być powiązane z typem lokalizacji czynności konserwacyjnych. Wybierz **Dodaj wiersz** i wybierz typy składnika majątku. Jeśli w tym miejscu zostaną dodane typy składnika majątku, tylko składniki majątku z tymi typami mogą być instalowane w lokalizacji czynności konserwacyjnych przy użyciu tego typu lokalizacji czynności konserwacyjnych. Jeśli nie wybrano żadnych typów składnika majątku na skróconej karcie **Typy składników majątku**, można zainstalować wszystkie typy składnika majątku.
9. Na skróconej karcie **Plany konserwacji** wybierz plany konserwacji, które powinny być automatycznie skonfigurowane w nowych lokalizacjach czynności konserwacyjnych przy użyciu tego typu lokalizacji czynności konserwacyjnych. Wybierz **Dodaj wiersz** i wybierz plany konserwacji. Jeśli dodasz w tym miejscu plany konserwacji, tylko te plany mogą być używane w lokalizacji czynności konserwacyjnych przy użyciu tego typu lokalizacji czynności konserwacyjnych.
10. Na skróconej karcie **Wymagania atrybutu składnika majątku** skonfiguruj atrybuty składnika majątku, które powinny być automatycznie skonfigurowane w nowych lokalizacjach czynności konserwacyjnych przy użyciu tego typu lokalizacji czynności konserwacyjnych. Wybierz **Dodaj wiersz** i wybierz atrybut. Te wymagania atrybutu funkcjonują jako wytyczne. Nie są one sprawdzane pod kątem atrybutów ustawionych na składniku majątku (**Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku** > wybierz składnik majątku na stronie listy > karta **Ogólne** > przycisk **Atrybuty**). Wymagania dotyczące atrybutów są wyświetlane podczas instalowania składników majątku w lokalizacjach czynności konserwacyjnych.
11. Na skróconej karcie **Dozwolone typy** wybierz typy lokalizacji czynności konserwacyjnych, które powinny być dozwolone dla typów podrzędnych lokalizacji czynności konserwacyjnych związanych z nadrzędnym typem lokalizacji czynności konserwacyjnych, który korzysta z wybranego typu lokalizacji czynności konserwacyjnych.
12. Na skróconej karcie **Atrybuty** wybierz atrybuty lokalizacji czynności konserwacyjnych, które powinny być automatycznie skonfigurowane w lokalizacjach czynności konserwacyjnych przy użyciu tego typu lokalizacji czynności konserwacyjnych. Wybierz **Dodaj wiersz** i wybierz atrybut.


>[!NOTE] 
>Na skróconej karcie **Ogólne** można uzyskać przegląd liczby typów składników majątku, planów konserwacji, wymagań dotyczących atrybutów składników majątku, dozwolonych typów, atrybutów i lokalizacji czynności konserwacyjnych, które są skonfigurowane na typ lokalizacji czynności konserwacyjnych. Pole **Lokalizacje czynności konserwacyjnych** pokazuje liczbę lokalizacji czynności konserwacyjnych, które używają typu lokalizacji czynności konserwacyjnych. Można użyć przycisku **Kopiuj**, aby skopiować ustawienia z typu lokalizacji czynności konserwacyjnych do wybranego typu lokalizacji czynności konserwacyjnych.
