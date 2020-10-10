---
title: Tworzenie lokalizacji czynności konserwacyjnych
description: W tym temacie opisano sposób tworzenia lokalizacjach czynności konserwacyjnych w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetFunctionalLocationCopyStructure, EntAssetFunctionalLocationCreate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 37da9d59e4e9cf84238f6798a1aa7de72ff91f02
ms.sourcegitcommit: c986d5234b81d31cc6d054298be6f6ec92c1754c
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/25/2020
ms.locfileid: "3888845"
---
# <a name="create-functional-locations"></a>Tworzenie lokalizacji czynności konserwacyjnych

[!include [banner](../../includes/banner.md)]

 

W tym temacie opisano sposób tworzenia lokalizacjach czynności konserwacyjnych w module Zarządzanie składnikami majątku.

Tworząc strukturę lokalizacji czynności konserwacyjnych, należy pamiętać, że po utworzeniu lokalizacji czynności konserwacyjnych nie można jej przenieść z oryginalnej lokalizacji. Oznacza to, że przed rozpoczęciem ich tworzenia w module Zarządzanie składnikami majątku należy starannie rozważyć strukturę lokalizacji czynności konserwacyjnych. W razie potrzeby można usunąć niepotrzebną lokalizację czynności konserwacyjnych, pod warunkiem, że nie była jeszcze używana.

Aby móc pracować z lokalizacjami czynności konserwacyjnych, zacznij od utworzenia dwóch „kategorii” lokalizacji czynności konserwacyjnych:

- Utwórz *jedną* domyślną lokalizację czynności konserwacyjnych bez lokalizacji podrzędnych. Ta lokalizacja czynności konserwacyjnych jest używana tylko jako standardowa lokalizacja dla składników majątku podczas tworzenia nowych składników majątku.  
- Utwórz struktury lokalizacji czynności konserwacyjnych wymaganych do zarządzania zadaniami konserwacji w firmie.

## <a name="create-a-default-functional-location"></a>Tworzenie domyślnej lokalizacji czynności konserwacyjnych

Podczas korzystania z lokalizacji czynności konserwacyjnych, rozpocznij od utworzenia jednej lokalizacji domyślnej, która będzie używana podczas tworzenia nowych składników majątku. Ta lokalizacja czynności konserwacyjnych jest tą, która została wybrana pod linkiem **Zarządzanie składnikami majątku** > **Ustawienia** > **Parametry zarządzania składnikami majątku** > **Składniki majątku** > pole **Domyślna lokalizacja czynności konserwacyjnych**. Domyślna lokalizacja czynności konserwacyjnych może być użyta podczas tworzenia nowych składników majątku i jeśli nie ustawiono struktury czynności konserwacyjnych dla tych składników majątku.

1. Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Lokalizacje czynności konserwacyjnych** > **Wszystkie lokalizacje czynności konserwacyjnych**.  
2. W polu **Wszystkie lokalizacje czynności konserwacyjnych** wybierz **Nowe**.
3. Wstaw identyfikator w polu **Lokalizacja czynności konserwacyjnych** np. „0000” lub „Domyślne”, aby wskazać, że jest to specjalna lokalizacja czynności konserwacyjnych.
4. Wstaw nazwę domyślnej lokalizacji czynności konserwacyjnych w polu **Nazwa**.
5. *Nie* wybieraj elementu nadrzędnego w polu **Nadrzędne** – zostaw to pole puste.
6. W polu **Typ lokalizacji czynności konserwacyjnych** wybierz typ lokalizacji czynności konserwacyjnych do używania dla domyślnej lokalizacji czynności konserwacyjnych. Zobacz temat [Typy lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-types.md), aby dowiedzieć, jak skonfigurować typy lokalizacji czynności konserwacyjnych.
7. Kliknij przycisk **OK**. Nie należy dodawać dalszych danych do tej lokalizacji czynności konserwacyjnych, ponieważ jest ona używana tylko jako tymczasowa lokalizacja dla nowych składników majątku, dopóki nie zainstalujesz zasobów w lokalizacjach czynności konserwacyjnych używanych przez firmę.

## <a name="create-functional-locations"></a>Tworzenie lokalizacji czynności konserwacyjnych

Poniższa procedura opisuje sposób tworzenia lokalizacji czynności konserwacyjnych wymaganych do zarządzania konserwacją w firmie.

1. Wybierz **Zarządzanie składnikami majątku** > **Wspólne** > **Lokalizacje czynności konserwacyjnych** > **Wszystkie lokalizacje czynności konserwacyjnych**. Można utworzyć lokalizację czynności konserwacyjnych z widoku siatki lub widoku szczegółów.
2. Wybierz przycisk **Nowa**.
3. Wstaw identyfikator w polu **Lokalizacja czynności konserwacyjnych**.
4. Wstaw nazwę lokalizacji czynności konserwacyjnych w polu **Nazwa**.
5. Jeśli lokalizacja czynności konserwacyjnych jest podlokalizacją w strukturze, wybierz lokalizację nadrzędną w polu **Nadrzędna**.
6. Wybierz typ pola w polu **Typ lokalizacji czynności konserwacyjnych**.
7. Kliknij przycisk **OK**.
8. Wybierz lokalizację czynności konserwacyjnych i kliknij przycisk **Edytuj**, aby dodać dalsze informacje.

>[!NOTE]
>W zależności od konfiguracji stanów cyklu życia lokalizacji czynności konserwacyjnych może być trzeba utworzyć wszystkie lokalizacje podrzędne dla lokalizacji czynności konserwacyjnych, a następnie zmienić stan cyklu życia lokalizacji czynności konserwacyjnych, zanim będzie można rozpocząć instalowanie składników majątku. Aby dowiedzieć się więcej o instalowaniu składników majątku, zobacz temat [Instalowanie składników majątku w lokalizacjach czynności konserwacyjnych](../functional-locations/install-objects-on-functional-locations.md). Aby dowiedzieć się więcej o konfigurowaniu stanów cyklu życia lokalizacji czynności konserwacyjnych, zobacz temat [Stany cyklu życia lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-stages.md).

W widoku Szczegóły zobaczysz skrócone karty, na których można dodawać i edytować informacje o lokalizacji czynności konserwacyjnych.

## <a name="general-information"></a>Informacje ogólne

Ta sekcja zawiera omówienie informacji nadrzędnych i podrzędnych w strukturze lokalizacji czynności konserwacyjnych. W sekcji **Szczegóły** można zobaczyć liczbę atrybutów składników majątku, planów konserwacji i składników majątku związanych z lokalizacją czynności konserwacyjnych. W sekcji **Zapasy** można wybrać oddział i magazyn, z którym jest powiązana lokalizacja czynności konserwacyjnych. Lokacja i magazyn są używane w połączeniu z prognozami pozycji zlecenia pracy. Podczas tworzenia prognozy zapasu, informacje o lokacji i magazynie z lokalizacji czynności konserwacyjnych składnika majątku są używane automatycznie. W sekcji **Stan cyklu życia** zostanie wyświetlona informacja o stanie cyklu życia lokalizacji czynności konserwacyjnych.

## <a name="installed-assets"></a>Zainstalowane składniki majątku

Aby dowiedzieć się więcej o instalowaniu składników majątku, zobacz temat [Instalowanie składników majątku w lokalizacjach czynności konserwacyjnych](../functional-locations/install-objects-on-functional-locations.md). Aby wyświetlić więcej pól na skróconej karcie, można skorzystać z przycisku **Widok** na tej skróconej karcie. Pola **Ważne od** i **Podrzędny składnik majątku** mogą być widoczne na siatce.

## <a name="asset-attribute-requirements"></a>Wymagania atrybutu składnika majątku

Na tej skróconej karcie można dodać określone wymagania dotyczące atrybutów dla składników majątku instalowanych w lokalizacji czynności konserwacyjnych. Te wymagania są przeznaczone wyłącznie do celów informacyjnych. Nie uniemożliwiają one instalowania składników majątku z innymi wymaganiami dotyczącymi atrybutów. Wybierz **Dodaj wiersz** i wybierz typ atrybutu. Następnie wprowadź odpowiednią **Wartość**, wybierz próg w polu **Kryteria progu** i zapisz rekord.

## <a name="maintenance-plans-and-maintenance-rounds"></a>Plany konserwacji i Serie czynności konserwacyjnych

W tym miejscu można dodać plany konserwacji i serie czynności konserwacyjne do lokalizacji czynności konserwacyjnych, w tym datę początkową. Składniki majątku zainstalowane w lokalizacji czynności konserwacyjnych mogą mieć skonfigurowane inne plany konserwacji. Wszystkie plany konserwacji i serie czynności konserwacyjnych mogą być używane do planowania wpisów kalendarza składników majątku dla lokalizacji czynności konserwacyjnych i aktualnie zainstalowanych składników majątku.

>[!NOTE]
>W przypadku aktualizowania ustawień typów składników majątku, marek składników majątku oraz modeli składników majątku w planach konserwacji w widoku szczegółowym **Wszystkie lokalizacje czynności konserwacyjnych** > na karcie skróconej **Plany konserwacji** po zaplanowaniu planów konserwacji, istniejące wpisy harmonogramu konserwacji związane z tą lokalizacją czynności konserwacyjnych są usuwane automatycznie. Aby utworzyć nowe wpisy harmonogramu, które odpowiadają zaktualizowaniu ustawień planu konserwacji w lokalizacji czynności konserwacyjnych, należy uruchomić nowy harmonogram planu konserwacji dla tej lokalizacji czynności konserwacyjnych. 

## <a name="address"></a>Adres 

Umożliwia wstawienie adresu lokalizacji czynności konserwacyjnych na karcie skróconej **Adres**. Adresy w lokalizacjach czynności konserwacyjnych są dziedziczone, co oznacza, że jeśli dla lokalizacji podrzędnej nie zdefiniowano adresu, używany jest adres lokalizacji nadrzędnej.

## <a name="workers"></a>Pracownicy

Na tej karcie skróconej można dodawać pracowników do lokalizacji czynności konserwacyjnych, a także wybierać lokalizację czynności konserwacyjnych jako podstawową dla pracownika. 

## <a name="attributes"></a>Atrybuty

Na tej skróconej karcie można ustawić wartości dla atrybutów lokalizacji czynności konserwacyjnych. Te atrybuty mogą służyć do opisywania właściwości lub charakterystyki dotyczącej lokalizacji czynności konserwacyjnych, na przykład właściwości strukturalnych, typów budynków, opisów obszarów lub lokalizacji pod lub pod ziemią.

Wybierz **Dodaj wiersz** i wybierz typ atrybutu. Następnie należy wstawić **Wartość** powiązaną z typem atrybutu i zapisać rekord.

## <a name="financial-dimensions"></a>Wymiary finansowe

Można wybrać wymiary finansowe dla lokalizacji czynności konserwacyjnych. [Typu lokalizacji czynności konserwacyjnych](../setup-for-functional-locations/functional-location-types.md) można skonfigurować, aby umożliwić automatyczną aktualizację wymiarów finansowych z lokalizacji czynności konserwacyjnych. Oznacza to, że składniki majątku zainstalowane w wymiarze finansowym automatycznie uzyskują wymiary finansowe dla lokalizacji czynności konserwacyjnych. Jest to przydatne, jeśli chcesz mieć różne centra kosztów zależnie od lokalizacji.

Jeśli dane dotyczące **Oddziału**, **Magazynu**, **Adresu** i **Wymiarów finansowych** są aktualizowane w nadrzędnej lokalizacji czynności konserwacyjnych, powiązane podrzędne lokalizacje czynności konserwacyjnych można odpowiednio aktualizować, o ile wybór zostanie dokonany podczas aktualizacji. Zostanie otwarte okno dialogowe z opcjami aktualizacji.

## <a name="copy-a-functional-location-structure"></a>Kopiuj strukturę lokalizacji czynności konserwacyjnych

Jeśli firma ma kilka lokalizacji czynności konserwacyjnych o podobnych strukturach lokalizacji, można skorzystać z funkcji kopiowania w module Zarządzanie zasobami, aby szybko tworzyć wiele podobnych hierarchii lokalizacji. Podczas kopiowania konkretnej lokalizacji czynności konserwacyjnych lub całej struktury nowa lokalizacja lub struktura ma taką samą nazwę jak skopiowana. Po wykonaniu procedury kopiowania można łatwo zmienić nazwę lub inne ustawienia w nowej lokalizacji czynności konserwacyjnych, pod warunkiem, że będzie to miało stan czasu trwania lokalizacji czynności konserwacyjnych wybrany dla nowej lokalizacji czynności konserwacyjnych.

1. W menu **Wszystkie lokalizacje czynności konserwacyjnych**wybierz lokalizację czynności konserwacyjnych, którą chcesz skopiować. Można na przykład wybrać najpopularniejszą lokalizację (nadrzędną), aby skopiować całą strukturę lokalizacji czynności konserwacyjnych, w tym lokalizacje podrzędne.
2. Wybierz przycisk **Kopiuj strukturę lokalizacji czynności konserwacyjnych**. Lokalizacja wybrana na stronie listy jest wyświetlana w polu **Kopiuj z**.
3. Wstaw nazwę nowej lokalizacji w polu **Nowa lokalizacja czynności konserwacyjnych**.
4. W polu **element nadrzędny do wklejenia w elemencie** należy wstawić identyfikator nadrzędny, tylko jeśli tworzona lokalizacja powinna być częścią istniejącej struktury lokalizacji czynności konserwacyjnych.
5. Kliknij przycisk **OK**. Nowa struktura lokalizacji czynności konserwacyjnych jest pokazana na karcie **Wszystkie lokalizacje czynności konserwacyjnych**.

>[!NOTE]
>Podczas kopiowania struktury lokalizacji czynności konserwacyjnych stany cyklu lokalizacji czynności konserwacyjnych w nowej strukturze są ustawiane jako „pierwszy stan” utworzone dla lokalizacji czynności konserwacyjnych. Możliwość zmiany nazwy lub usunięcia lokalizacji czynności konserwacyjnych za pomocą przycisków **Zmień nazwę** i **Usuń** na karcie **Wszystkie lokalizacje czynności konserwacyjnych** zależy od bieżącego stanu cyklu eksploatacji lokalizacji czynności konserwacyjnych.

## <a name="delete-a-functional-location"></a>Usuwanie lokalizacji czynności konserwacyjnych

Lokalizację czynności konserwacyjnych z powiązanymi lokalizacjami podrzędnymi można usunąć, jeśli w żadnej lokalizacji czynności konserwacyjnych, którą próbujesz usunąć, nie zainstalowano żadnych składników majątku oraz jeśli zezwala na to aktualny stan cyklu życia lokalizacji czynności konserwacyjnych.

1. W menu **Wszystkie lokalizacje czynności konserwacyjnych** wybierz lokalizację czynności konserwacyjnych, którą chcesz usunąć.
2. W razie potrzeby zaktualizuj lokalizację czynności konserwacyjnych do stanu cyklu życia, który umożliwia usunięcie lokalizacji czynności konserwacyjnych.
3. Wybierz opcję **Usuń**.

>[!NOTE]
>Jeśli nie można usunąć lokalizacji czynności konserwacyjnych, można ją obsługiwać, konfigurując w tym celu stan cyklu życia lokalizacji czynności konserwacyjnych. Na przykład można skonfigurować etap „Uznany za odpadki” lub „Usunięty”, który nie powinien być aktywnym etapem, w formularzu **Stany czasu trwania lokalizacji czynności konserwacyjnych**.
