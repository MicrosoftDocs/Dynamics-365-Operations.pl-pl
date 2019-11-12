---
title: Instalowanie składników majątku w lokalizacjach czynności konserwacyjnych
description: W tym temacie opisano sposób instalowania składników majątku w lokalizacjach czynności konserwacyjnych modułu Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 06/25/2019
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
ms.openlocfilehash: c585bce468f87a32204893ea20ce6954e92b0e38
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571813"
---
# <a name="install-assets-on-functional-locations"></a>Instalowanie składników majątku w lokalizacjach czynności konserwacyjnych

[!include [banner](../../includes/banner.md)]

 

Po utworzeniu struktur lokalizacji czynności konserwacyjnych następnym krokiem jest zainstalowanie składników majątku w odpowiednich lokalizacjach czynności konserwacyjnych. W tym temacie opisano sposób instalowania składników majątku w tych lokalizacjach czynności konserwacyjnych modułu Zarządzanie składnikami majątku. Aby uzyskać więcej informacji o tworzeniu składników majątku, zobacz temat [Składniki majątku](../objects/introduction-to-objects.md).

Jeśli została utworzona struktura składników majątku, musi ona być zainstalowana w całości w lokalizacji czynności konserwacyjnych. Dlatego tylko nadrzędne składniki majątku (składniki majątku najwyższego poziomu, które nie mają nadrzędnych składników majątku) mogą być wybierane w lokalizacji czynności konserwacyjnych. Wszystkie powiązane podrzędne składniki majątku zostaną również zainstalowane w lokalizacji czynności konserwacyjnych. Podczas instalowania składników majątku w lokalizacji czynności konserwacyjnych wymiary finansowe lokalizacji czynności konserwacyjnych mogą być automatycznie przenoszone do tych wymiarów, w zależności od konfiguracji typu lokalizacji czynności konserwacyjnych wybranej dla lokalizacji czynności konserwacyjnych. Aby uzyskać więcej informacji na temat konfigurowania typów lokalizacji czynności konserwacyjnych, zobacz temat [Typy funkcjonalnej czynności konserwacyjnych](../setup-for-functional-locations/functional-location-types.md).

> [!NOTE]
> Można skonfigurować typy składników majątku jako typ lokalizacji czynności konserwacyjnych używanej dla lokalizacji czynności konserwacyjnych. W takim przypadku podczas instalowania składników majątku w lokalizacji czynności konserwacyjnych na liście składników majątku, które można zainstalować w lokalizacji czynności konserwacyjnych, są wyświetlane tylko aktywa nadrzędne mające ten sam typ składników majątku.

Po zainstalowaniu składników majątku w lokalizacji czynności konserwacyjnych można zamienić nadrzędny składnik majątku lub strukturę składnika majątku stosownie do potrzeb. W przypadku instalowania środków trwałych należy wybrać nadrzędny składnik majątku, który ma zostać zastąpiony. Wszystkie powiązane składniki majątku również zostaną zastąpione. 


## <a name="install-an-asset-structure-on-a-functional-location"></a>Zainstaluj strukturę składnika majątku w lokalizacji czynności konserwacyjnych

1. Wybierz kolejno opcje **Zarządzanie składnikami majątku** \> **Wspólne** \> **Lokalizacje czynności konserwacyjnych** \> **Wszystkie lokalizacje czynności konserwacyjnych** lub **Aktywne lokalizacje czynności konserwacyjnych**.
2. Wybierz lokalizację czynności konserwacyjnych, w której ma zostać zainstalowany składnik majątku.
3. Wybierz opcję **Zainstaluj składnik majątku**.

    W sekcji **Atrybuty** jest wyświetlana lista wymagań dotyczących atrybutów składników majątku skonfigurowanych dla typu lokalizacji czynności konserwacyjnych wybranej dla lokalizacji czynności konserwacyjnych. Atrybuty są używane wyłącznie w celach informacyjnych. System nie sprawdza poprawności atrybutów w odniesieniu do atrybutów składnika majątku ustawionych dla instalowanego składnika majątku. Należy to sprawdzić po wybraniu składnika majątku w polu **Składnik majątku.**

4. W polu **Składnik majątku** wybierz nadrzędny składnik majątku, który ma zostać zainstalowany. Wszystkie powiązane podrzędne składniki majątku są automatycznie uwzględniane w instalacji.

    Sekcja **Atrybuty składniku majątku** po prawej stronie listy składników majątku zawiera atrybuty składników majątku związane z wybranym składnikiem majątku.

5. W polu **Data wprowadzenia** wybierz datę i godzinę rozpoczęcia obowiązywania instalacji składnika majątku. Po tej dacie i godzinie koszty składnika majątku i powiązanych z nim składników podrzędnych będą związane z lokalizacją czynności konserwacyjnych.

    > [!NOTE]
    > Atrybuty składnika majątku skonfigurowane dla składnika majątku zostaną dodane do sekcji **Składniki majątku**. Na przykład wymagania dotyczące atrybutu **Waga** zostały dodane jako wymóg zarówno w składnika majątku, jak i w lokalizacji czynności konserwacyjnych. Jeśli składnik majątku ma wymagania dotyczące atrybutu tego samego typu co lokalizacja czynności konserwacyjnych, wartości dotyczące atrybutów składnika majątku są wprowadzane w polach **Wartość**. W związku z tym można sprawdzić poprawność wartości składników majątku w odniesieniu do wymagań dotyczących atrybutów skonfigurowanych w lokalizacji czynności konserwacyjnych. Wymagania dotyczące atrybutów skonfigurowane w lokalizacji czynności konserwacyjnych są oznaczone znacznikiem wyboru.

6. Kliknij przycisk **OK**.

    > [!NOTE]
    > Aby zmienić instalację składnika majątku, instalując go w nowym lokalizacji czynności konserwacyjnych, należy wykonać kroki od 1 do 6 tej procedury. W przypadku instalowania składnika majątku w nowej lokalizacji czynności konserwacyjnych składnik jest automatycznie odinstalowywany z poprzedniej lokalizacji czynności konserwacyjnych. Wszystkie aktywne żądania obsługi lub zlecenia produkcyjne utworzone na danym składniku majątku przed zainstalowaniem go w nowej lokalizacji czynności konserwacyjnych **nie** są automatycznie przenoszone do nowej lokalizacji czynności konserwacyjnych. Jeśli te żądania obsługi i zlecenia są nadal wymagane dla składnika majątku, należy je ponownie utworzyć ręcznie po zainstalowaniu składnika majątku w nowej lokalizacji.

7. Aby wyświetlić listę wszystkich składników majątku, w tym składników podrzędnych, które są zainstalowane w lokalizacji czynności konserwacyjnych, wybierz lokalizację czynności konserwacyjnych na stronie **Wszystkie lokalizacje czynności konserwacyjnych**, a następnie wybierz pozycję **Składniki majątku**.
8. Aby wyświetlić listę aktywnych zgłoszeń konserwacyjnych, aktywnych zleceń produkcyjnych lub rejestracji usterek powiązanych ze składnikami majątku zainstalowanymi w lokalizacji czynności konserwacyjnych, wybierz lokalizację czynności konserwacyjnych na stronie **Wszystkie lokalizacje czynności konserwacyjnych**, a następnie wybierz **Żądania**, **Zlecenia produkcyjne** lub **Błędy**.

> [!NOTE]
> Po zmianie danych dotyczących składników majątku są one automatycznie aktualizowane w lokalizacji czynności konserwacyjnych, w której jest zainstalowany dany składnik majątku. Ta aktualizacja automatyczna dotyczy zmian w żądaniach obsługi, zleceniach produkcyjnych, rejestracjach błędów składników majątku, rejestracjach przestojów i rejestracji miar składników majątku.

## <a name="automatically-create-one-asset-on-a-functional-location"></a>Automatyczne tworzenie jednego składnika majątku w lokalizacji czynności konserwacyjnych

Istnieje możliwość skonfigurowania etapów lokalizacji czynności konserwacyjnych i typów lokalizacji czynności konserwacyjnych w celu obsługi automatycznego tworzenia *jednego* składnika majątku w lokalizacji czynności konserwacyjnych. Składnik majątku uzyskuje taki sam identyfikator i nazwę co lokalizacja czynności konserwacyjnych. Ta funkcjonalność może być przydatna w przypadku obsługi dużego statycznego składnika majątku, takiego jak budynek.

Aby można było automatycznie utworzyć składnik majątku w lokalizacji czynności konserwacyjnych, muszą być dostępne następujące dane konfiguracyjne:

- Utwórz typ lokalizacji czynności konserwacyjnych w celu obsługi automatycznego tworzenia składnika majątku. W polu **Typ składnika majątku** wybierz typ składnika majątku. Aby uzyskać więcej informacji, zobacz [Typy lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-types.md).
- Utwórz stan cyklu życia lokalizacji czynności konserwacyjnych w celu obsługi automatycznego tworzenia składnika majątku. Ustaw wartość **Tak** opcji **Utwórz składnik majątku**. Aby uzyskać więcej informacji, zobacz [Stany cyklu życia lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-stages.md).

Gdy dane konfiguracyjne są dostępne, możesz przystąpić do tworzenia składnika majątku.

1. Na stronie **Wszystkie lokalizacje czynności konserwacyjnych** upewnij się, że lokalizacja czynności konserwacyjnych, w której ma zostać automatycznie utworzony składnik majątku, korzysta z typu lokalizacji czynności konserwacyjnych utworzonego w tym celu.
2. Wybierz lokalizację czynności konserwacyjnych na liście.
3. Wybierz pozycję **Aktualizuj stan lokalizacji czynności konserwacyjnych**, a następnie wybierz stan cyklu życia utworzony w tym celu. Jeden składnik majątku jest teraz automatycznie instalowany w lokalizacji czynności konserwacyjnych. Tan składnik majątku ma tę samą nazwę co lokalizacja czynności konserwacyjnych.
