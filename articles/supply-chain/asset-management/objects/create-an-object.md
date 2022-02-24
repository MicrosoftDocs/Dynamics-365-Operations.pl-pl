---
title: Tworzenie składnika majątku
description: W tym temacie opisano sposób tworzenia składnika majątku w Zarządzaniu składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage, EntAssetObjectTableCopyStructure, EntAssetObjectTableCreate
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 28c4685c3b6f543324953cd03646d5b15fdb8c59
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5019436"
---
# <a name="create-an-asset"></a>Tworzenie składnika majątku

[!include [banner](../../includes/banner.md)]

 

W tym temacie opisano sposób tworzenia składnika majątku w Zarządzaniu składnikami majątku.

1. Kliknij **Zarządzanie składnikami majątku** > **Wspólne** > **składniki majątku** > **Wszystkie składniki majątku** lub **Aktywne składniki majątku**.
2. Kliknij przycisk **Nowe**.
3. W oknie dialogowym **Tworzenie składników majątku** wstaw dane dotyczące **Składnika majątku** (identyfikator składnika majątku) oraz nazwę składnika majątku. Wybierz datę i godzinę składnika majątku w polu **Data wprowadzenia**. Od tej daty można instalować składnik majątku w lokalizacji czynności konserwacyjnych, a także przenosić i zastępować składnik majątku w strukturze składników majątku.
4. W polu **Typ składnika majątku** wybierz typ składnika majątku (pole obowiązkowe). W razie potrzeby wybierz pozycję **Producent składnika majątku** i **Model składnika majątku** dla danego zasobu. Jeśli tylko jeden produkt został skonfigurowany, ten produkt jest automatycznie wybierany w polu **Producent składnika majątku**. Opcje dostępne w polach **Producent składnika majątku** i **Model składnika majątku** zależą od konfiguracji w artykule [Producenci i modele składnika majątku](../setup-for-objects/product-and-model.md)
5. W grupie **Nadrzędny składnik majątku** pole **Składnik majątku** jest domyślnie puste. Jeśli jest to wymagane, można wybrać nadrzędny składnik majątku, a następnie wszystkie pola w grupie **Nadrzędny składnik majątku** zostaną automatycznie wypełnione.
    >[!NOTE]  
    >Po wybraniu nadrzędnego składnika majątku dwie lub trzy karty są dostępne: karta **Moje składniki majątku** zawiera składniki majątku związane z lokalizacjami czynności konserwacyjnych, do których może zostać przydzielony konserwator zalogowany w systemie. Jeśli lokalizacje czynności konserwacyjnych nie są skonfigurowane dla konserwatora w formularzu [Konserwatorzy i grupy konserwatorów](../setup-for-objects/workers-and-worker-groups.md), karta **Moje składniki majątku** nie będzie widoczna. Karta **Aktywne składniki majątku** zawiera listę wszystkich składników majątku ze stanem cyklu życia zasobu „Aktywny”. Na karcie **Widok składników majątku** jest wyświetlany widok drzewa lokalizacji czynności konserwacyjnych i składników majątku zainstalowanych w tych lokalizacjach.

6. Domyślna lokalizacja czynności konserwacyjnych, która została ustawiona, jest sugerowana dla składników majątku w grupie **Składniki majątku** > pole **Lokalizacja czynności konserwacyjnych**. W razie potrzeby wybierz inną lokalizację czynności konserwacyjnych.

    >[!NOTE]
    >Po utworzeniu składnika majątku można go zainstalować w innej lokalizacji czynności konserwacyjnych, jeśli jest to wymagane. W lokalizacji czynności konserwacyjnych można instalować tylko składniki majątku najwyższego poziomu (składniki majątku bez bieżącego nadrzędnego składnika majątku). Oznacza to, że można zainstalować składniki majątku najwyższego poziomu, jak również wszystkie podrzędne składniki majątku w wybranej lokalizacji czynności konserwacyjnych. Dowiedz się więcej o instalowaniu składników majątku w lokalizacjach czynności konserwacyjnych w artykule [Wprowadzenie do lokalizacji czynności konserwacyjnych](../functional-locations/introduction-to-functional-locations.md).

7. Kliknij przycisk **OK**.
8. Wybierz składnik majątku na liście **Wszystkie składniki majątku** i kliknij przycisk **Edytuj**, aby dodać dodatkowe informacje do składnika majątku.

## <a name="general-information"></a>Informacje ogólne

Lokalizacja czynności konserwacyjnych, do której jest powiązany składnika majątku, jest wyświetlana w polu **Lokalizacja czynności konserwacyjnych**. Jeśli składnik majątku jest nadrzędny, liczba elementów podrzędnych wobec tego składnika majątku jest wyświetlana w polu **Podrzędny**. Jeśli składnik majątku jest podrzędny względem składnika istniejącego, identyfikator nadrzędnego składnika majątku jest wyświetlany w polu **Nadrzędny**.

Można edytować informacje **Producent składnika majątku** oraz **Model składnika majątku** używane do zarządzania częściami zamiennymi, alternatywnymi częściami zamiennymi i domyślnymi typami pracy. Więcej informacji można uzyskać w artykule [Producenci i modele składników majątku](../setup-for-objects/product-and-model.md). W razie potrzeby można również dodać informacje **Rok modelu** i **Numer seryjny**.

**Bieżący stan cyklu życia** jest używany do definiowania, czy składnik majątku jest aktywny czy nieaktywny. Podczas tworzenia składnika majątku etap jest zawsze ustawiany na pierwszy etap w grupie etapów składników majątku. Gdy wszystko będzie gotowe do aktywowania składnika zasobu, kliknij przycisk **Aktualizuj stan składnika majątku** i wybierz stan cyklu życia zdefiniowany jako „aktywny środek majątku”, a następnie kliknij przycisk **OK**.

**Uwaga:** gdy składnik majątku jest ustawiony na „nieaktywny”, nie jest już możliwe tworzenie zleceń pracy dla tego składnika majątku. Ponadto nie można zaplanować zadań konserwacji zapobiegawczej dla nieaktywnego składnika majątku.

Pola **Poziom usługi** i **Krytyczność** odnoszą się do zleceń pracy utworzonych dla składnika majątku. Pola pokazują wartości **Poziom usługi** i **Krytyczności** obliczone dla bieżącego ustawienia dla składnika majątku. Aby dowiedzieć się więcej o konfigurowaniu tych wartości, zobacz artykuły [Poziomy usług składnika majątku](../setup-for-objects/object-priorities.md) oraz [Krytyczności składników majątku](../setup-for-objects/object-criticalities.md).

## <a name="asset"></a>Składnik majątku

Można wybrać **Zasób** dla składnia majątku. Wybór zasobu określa, który kalendarz jest używany do planowania zlecenia pracy. Wybór zasobu jest często używany w przypadku środków trwałych. Zasoby i grupy zasobów są skonfigurowane w menu **Administrowanie organizacją** > **Zasoby** > **Grupy zasobów** lub **Zasoby**.

W polu **Liczba środków trwałych** można wybrać środek trwały dla składnika majątku. Jest to istotne, jeśli składnik majątku jest powiązany z projektem inwestycyjnym.

- Jeśli składnik majątku jest powiązany ze środkiem trwałym, można utworzyć typ zlecenia pracy, który będzie używany dla zleceń pracy związanych z projektem inwestycyjnym. 
- Informacje na temat środków trwałych dla składnika majątku są powiązane z modułem **Środki trwałe** w Dynamics 365 Supply Chain Management. Oznacza to, że w menu **Środki trwałe** > **Środki trwałe** > **Środki trwałe** można uzyskać przegląd projektów zarządzania aktywami, które mogą być związane z środka trwałego, wybierając zasób na liście i wyświetlanie zawartości w okienku **Informacje pokrewne** > sekcja **Powiązane projekty**.


## <a name="details"></a>Szczegóły

W polu **Data rozpoczęcia aktywności** wyświetlana jest data aktualizacji stanu cyklu życia składnika majątku do stanu aktywnego (zobacz temat [Stany cyklu życia składnika majątku](../setup-for-objects/object-stages.md), aby dowiedzieć się więcej o konfiguracji stanów cyklu życia składnika majątku). Jeśli zasób nie jest już aktywny, a stan cyklu życia zasobu został zaktualizowany do stanu nieaktywnego cyklu życia, Data, od której zasób jest nieaktywny, jest wyświetlana w polu **aktywny do.** Jeśli to konieczne, te daty można zmienić ręcznie.

W razie potrzeby można wstawić oczekiwaną datę zastąpienia składnika majątku w polu **Data wymiany**. Wartość szacunkowa zastąpienia środka trwałego można wstawić w polu **Wartość zastępcza**. Przykład: można użyć informacji na temat wymiany do porównania ich z kosztami utrzymania składnika majątku, a następnie podjąć decyzję o zakupie nowego składnika majątku, jeśli koszty utrzymania istniejącego składnika majątku szybko rosną.

## <a name="notes"></a>Notatki

Można dodać notatki dotyczące składnika majątku na skróconej karcie **Notatki**. Kliknij przycisk **Dodaj sygnaturę czasową** przed napisaniem notatki, jeśli chcesz dodać do notatki informacje o użytkowniku i datę/znacznik czasu.

## <a name="attributes"></a>Atrybuty

Na tej skróconej karcie można ustawić wartości dla atrybutów składników majątku. Te atrybuty mogą służyć do opisywania właściwości lub właściwości charakterystycznych dla składnika majątku, na przykład rozmiaru, wagi lub konfiguracji maszyny.

Kliknij przycisk **Dodaj wiersz** i wybierz typ atrybutu. Następnie należy wstawić **Wartość** powiązaną z typem atrybutu i zapisać rekord.

>[!NOTE] 
>Można uzyskać przegląd typów atrybutów zasobów i ich relacji ze składnikami majątku w **Atrybucie składnika majątku** i **przeglądzie atrybutów składnika majątku**. Aby uzyskać więcej informacji, zobacz temat [Omówienie atrybutu składnika majątku](../objects/object-specification-overview.md).

## <a name="vendor"></a>Dostawca

Na skróconej karcie **Dostawca** wybierz konto dostawcy dla składnika majątku. Ponadto, jeśli udzielono gwarancji dostawcy, można wstawić informacje gwarancyjne tutaj.

## <a name="address"></a>Adres

Na skróconej karcie **Adres** można wstawić adres urządzenia. Jeśli nie zostanie wprowadzony żaden adres składnika majątku, używa on adresu składnika nadrzędnego, o ile ten ma adres. Jeśli żaden adres nie jest powiązany ze składnikiem majątku ani jego elementem nadrzędnym w hierarchii składników majątku, może być używany adres lokalizacji czynności konserwacyjnych, na której składnik majątku jest zainstalowany. Jeśli ta lokalizacja czynności konserwacyjnych nie ma powiązanego z nią adresu, używany jest adres nadrzędnej lokalizacji czynności konserwacyjnych składnika majątku.

## <a name="asset-management-plans"></a>Plany zarządzania składnikami majątku

Plany konserwacji służą do planowania zadań konserwacji zapobiegawczej w regularnych odstępach czasu w odniesieniu do składnika majątku. Na tej skróconej karcie można skonfigurować wiersze planu konserwacji dla wybranego składnika majątku. Serie czynności konserwacyjnych można konfigurować w odniesieniu do różnych składników majątku, na których trzeba wykonywać podobne zadania w regularnych odstępach czasu. Na karcie **Plany konserwacji lokalizacji czynności konserwacyjnych** są widoczne plany konserwacji związane z lokalizacją czynności konserwacyjnych, na której jest zainstalowany składnik majątku.

>[!NOTE]
>Usunięcie wiersza planu konserwacji lub serii czynności konserwacyjnych związanej ze składnikiem majątku w menu **Wszystkie składniki majątku** powoduje również automatyczne usunięcie wszystkich harmonogramów konserwacji ze stanem „Utworzono”, które zostały utworzone na podstawie tego planu konserwacji lub serii czynności konserwacyjnych.

## <a name="functional-location-maintenance-plans"></a>Plany konserwacji lokalizacji czynności konserwacyjnych

Na tej skróconej karcie można uzyskać omówienie planów konserwacji związanych z lokalizacją czynności konserwacyjnych, na której jest zainstalowany składnik majątku.

## <a name="maintenance-rounds"></a>Serie czynności konserwacyjnych

Na tej skróconej karcie można dodawać lub usuwać serie czynności konserwacyjnych, które są powiązane ze składnikiem majątku.

## <a name="financial-dimensions"></a>Wymiary finansowe

Można wybrać wymiary finansowe dla składnika majątku.
