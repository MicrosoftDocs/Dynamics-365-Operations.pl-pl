---
title: Konserwatorzy i grupy konserwatorów
description: W tym temacie wyjaśniono, jak działają konserwatorzy i grupy pracowników w module Zarządzanie składnikami majątku.
author: josaw1
manager: tfehr
ms.date: 06/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6cf7e8e796032b348cff5a77c10b376dbbeef974
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/02/2020
ms.locfileid: "3214788"
---
# <a name="maintenance-workers-and-worker-groups"></a>Konserwatorzy i grupy konserwatorów

[!include [banner](../../includes/banner.md)]

 

W tym temacie wyjaśniono, jak działają konserwatorzy i grupy pracowników w module Zarządzanie składnikami majątku. W module Zarządzanie składnikami majątku można łączyć konserwatorów z lokalizacjami czynności konserwacyjnych. (Aby uzyskać więcej informacji o lokalizacjach czynności konserwacyjnych, zobacz temat [Tworzenie lokalizacji czynności konserwacyjnych](../functional-locations/create-functional-locations.md)). Ta funkcja może być przydatna, jeśli na przykład planujesz zadanie konserwacji na komputerze znajdującym się w lokalizacji czynności konserwacyjnych 01, a chcesz przydzielić konserwatorów z tej samej lokalizacji do wykonania zadania.

Można również tworzyć grupy konserwatorów i kojarzyć z nimi konserwatorów. Ta funkcja jest przydatna, gdy wykonujesz proste planowanie zlecenia pracy i chcesz zaplanować grupę konserwatorów na zleceniu pracy. Możesz użyć konserwatorów i grupy konserwatorów do konfigurowania preferowanych konserwatorów i odpowiedzialnych konserwatorów. 


## <a name="create-workers"></a>Tworzenie pracowników

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Pracownicy** \> **Pracownicy**.
2. Wybierz **Nowy**, aby dodać nowego pracownika do listy.
3. W polu **Pracownik** wybierz pracownika.
4. Ustaw opcję **Aktywny** na **Tak**, aby zaplanować pracownika w zleceniach pracy.

    Na skróconej karcie **Ogólne** pola **Zasób** i **Opis** są wypełniane automatycznie, jeśli wybrano zasób dla pracownika. Pole **Kalendarz** jest również wypełniane automatycznie, pod warunkiem, że pracownik został skonfigurowany jako zasób i przydzielono kalendarz do tego zasobu na **stronie Zasoby** (**Administrowanie organizacją** \> **Zasoby** \> **Zasoby**).

5. Na skróconej karcie **Grupy** wybierz pozycję **Dodaj**, a następnie wybierz grupę konserwatorów dla pracownika. Pracownik może być związany z więcej niż jedną grupą.
6. W konfiguracji standardowej przynależność pracownika do grupy obowiązuje od daty dodania grupy i nigdy nie wygasa. Data ta jest wyświetlana w polu **Weszła w życie**. Aby wyświetlić pole **Weszła w życie**, wybierz opcję **Wyświetl**\>**Wszystkie**. Jeśli przynależność pracownika do grupy powinna być ograniczona do określonego okresu, należy użyć pól **Weszła w życie** i **Wygaśnięcie**, aby zdefiniować okres.
7. Na skróconej karcie **Lokalizacje czynności konserwacyjnych** wybierz pozycję **Dodaj**, a następnie lokalizację czynności konserwacyjnych dla konserwatora. Możesz również określić, która lokalizacja jest główną lokalizacją czynności konserwacyjnych dla pracownika.

    > [!NOTE]
    > Po dodaniu lokalizacji czynności konserwacyjnych do pracownika wszystkie aktywna składniki majątku, które są powiązane z tymi lokalizacjami czynności konserwacyjnych, są wyświetlane w różnych elementach menu, takich jak **Moje aktywne składniki majątku** i **Moje aktywne lokalizacje czynności konserwacyjnych**. Pojawiają się również w wyszukiwanych składników majątku, które są wyświetlane podczas tworzenia nowego składnika majątku, żądania konserwacji lub zlecenia pracy.

    Pola na skróconej karcie **Szczegóły** pokazują liczbę grup roboczych konserwacji i lokalizacje czynności konserwacyjnych, które są powiązane z wybranym konserwatorem.

## <a name="create-worker-groups"></a>Tworzenie grup pracowników

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Pracownicy** \> **Grupy konserwatorów**.
2. Wybierz **Nowy**, aby dodać nową grupę pracowników do listy.
3. W polu **Grupa konserwatorów** wprowadź identyfikator grupy.
4. W polu **Nazwa** wprowadź nazwę.
5. Na skróconej karcie **Pracownicy** wybierz pozycję **Dodaj**, a następnie wybierz grupę konserwatorów dla grupy pracownika. Aby uzyskać informacje dotyczące pól**Weszła w życie** i **Wygaśnięcie**, zobacz krok 6 w poprzedniej procedurze.
6. Jeśli grupa zasobów powinna być powiązana z wybraną grupą konserwatorów, wybierz opcję **Kopiuj z grupy zasobów**. W polu **Grupa** wybierz grupę zasobów, z której chcesz skopiować ustawienia kalendarza. Następnie w polu **Grupa pracowników** wybierz grupę pracowników, do której chcesz skopiować ustawienia kalendarza grupy zasobów. Ten krok jest istotny tylko wtedy, gdy chcesz, aby konserwatorzy używali kalendarza związanego z zasobem (centrum pracy) w trakcie planowania zlecenia pracy.

    Pole na skróconej karcie **Szczegóły** pokazuje liczbę konserwatorów skonfigurowanych w wybranej grupie konserwatorów.
