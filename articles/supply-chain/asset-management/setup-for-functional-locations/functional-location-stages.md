---
title: Stany cyklu życia lokalizacji czynności konserwacyjnych
description: W tym temacie opisano sposób konfigurowania stanów lokalizacji czynności konserwacyjnych i modeli cyklu życia w module Zarządzanie składnikami majątku.
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
ms.openlocfilehash: 11f784e4c17ad5b764cadd914f4959f4be160913
ms.sourcegitcommit: 747bcd25ce7c6c20ce9eaa0027e730f74d4fd6aa
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/23/2019
ms.locfileid: "1783511"
---
# <a name="functional-location-lifecycle-states"></a>Stany cyklu życia lokalizacji czynności konserwacyjnych

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W tym temacie opisano sposób konfigurowania stanów cyklu życia lokalizacji czynności konserwacyjnych i modeli cyklu życia w module Zarządzanie składnikami majątku. Stany cyklu życia lokalizacji czynności konserwacyjnych definiują stany, przez które może przechodzić lokalizacja czynności konserwacyjnych, np. utworzona, aktywna i zakończona. Wszystkie lokalizacje czynności konserwacyjnych, niezależnie od ich stanu cyklu życia, można wyświetlić na stronie listy **Wszystkie lokalizacje czynności konserwacyjnych**. Stan lokalizacji funkcjonalnej można zmienić, zaznaczając go na stronie listy **Wszystkie lokalizacje czynności konserwacyjnych** i wybierając pozycję **Aktualizuj stan lokalizacji czynności konserwacyjnych**.

## <a name="set-up-functional-location-lifecycle-states"></a>Ustawienia stanów cyklu życia lokalizacji czynności konserwacyjnych

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Ustawienia** > **Lokalizacje czynności konserwacyjnych** > **Stany cyklu życia**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy stan lokalizacji czynności konserwacyjnych.
3. Wstaw identyfikator stanu w polu **Stan cyklu życia** i nazwę stanu lokalizacji czynności konserwacyjnych w polu **Nazwa**. W polu **Modele cyklu życia** można zobaczyć liczbę modeli cyklu życia lokalizacji czynności konserwacyjnych, które używają stanu lokalizacji czynności konserwacyjnych.
4. Na skróconej karcie **Ogólne** wybierz opcję „Tak” na przełączniku **Aktywna**, jeśli lokalizacja czynności konserwacyjnych powinna być aktywna w tym stanie.
5. Wybierz „Tak” na przełączniku **Utwórz składniki majątku**, jeśli powinno być możliwe automatyczne tworzenie składników majątku o takiej samej nazwie jak lokalizacja czynności konserwacyjnych i zainstalować go w lokalizacji czynności konserwacyjnych w tym stanie.  
>[!NOTE]
>Ten przełącznik odnosi się do pola **Typ składnika majątku** na skróconej karcie **Ogólne** w formularzu **Typu lokalizacji czynności konserwacyjnych** (**Zarządzanie składnikami majątku** > **Ustawienia** > **Lokalizacje czynności konserwacyjnych** > **Typy lokalizacji czynności konserwacyjnych**).
6. Wybierz „Tak” na przełączniku **Zmień nazwę lokalizacji**, jeśli powinna być możliwa zmiana nazwy lokalizacji czynności konserwacyjnych w tym stanie.
7. Wybierz „Tak” na przełączniku **Nowe lokalizacje podrzędne**, jeśli powinno być możliwe dodawanie nowych lokalizacji podrzędnych do lokalizacji czynności konserwacyjnych w tym stanie.
8. Wybierz „Tak” na przełączniku **Zainstaluj składniki majątku**, jeśli powinno być możliwe instalowanie składników majątku w lokalizacji czynności konserwacyjnych w tym stanie.
9. Wybierz „Tak” na przełączniku **Usuń lokalizację czynności konserwacyjnych majątku**, jeśli powinno być możliwe usuwanie lokalizacji czynności konserwacyjnych w tym stanie.
10. Wybierz stan składnika majątku w polu **Stan cyklu życia**, jeśli chcesz, aby stan cyklu życia składnika majątku dla wszystkich składników majątku zainstalowanych w lokalizacji czynności konserwacyjnych był automatycznie aktualizowany w tym stanie. Przykład: jeśli zamkniesz lokalizację czynności konserwacyjnych i ustawisz stan cyklu życia lokalizacji czynności konserwacyjnych na „zakończony”, możesz chcieć automatycznie zmienić stan cyklu życia składnika majątku zainstalowanego w tej lokalizacji czynności konserwacyjnych na „nieużywany”.


>[!NOTE]
>Stany cyklu życia lokalizacji czynności konserwacyjnych, modele cyklu życia i typy są powiązane i używane w taki sam sposób jak stany cyklu życia zlecenia pracy, modele cyklu życia zlecenia pracy i typy zleceń pracy. 

## <a name="set-up-functional-location-lifecycle-models"></a>Konfigurowanie modeli cyklu życia lokalizacji czynności konserwacyjnych

Po utworzeniu stanów cyklu życia wymaganych dla lokalizacji funkcjonalnych można je podzielić na grupy. Można to zrobić, aby utworzyć przepływ modelu cyklu życia, który może być używany dla różnych typów lokalizacji czynności konserwacyjnych. Jako minimum należy utworzyć jeden standardowy model cyklu życia lokalizacji czynności konserwacyjnych.

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Ustawienia** > **Lokalizacje czynności konserwacyjnych** > **Modele cyklu życia**.
2. Wybierz pozycję **Nowy**, aby utworzyć nowy model cyklu życia.
3. Wstaw identyfikator modelu cyklu życia w polu **Model cyklu życia** i nazwę modelu cyklu życia w polu **Nazwa**. W polach **Typy lokalizacji czynności konserwacyjnych** i **Stany cyklów życia** można zobaczyć liczbę typów lokalizacji czynności konserwacyjnych, które używają modelu cyklu życia i liczbę stanów wybranych w modelu cyklu życia.
4. Na skróconej karcie **Stany cyklu życia** wybierz stany, które powinny być uwzględnione w modelu. W tym celu kliknij stan w sekcji **Pozostałe stany cyklu życia** i kliknij przycisk ![strzałki do przodu](media/02-setup-for-functional-locations.png).
5. Jeśli chcesz wybrać wszystkie dostępne stany dla modelu, kliknij przycisk ![Wybierz wszystkie dostępne etapy](media/03-setup-for-functional-locations.png). Wszystkie stany są przenoszone do sekcji **Wybrane cykle życia**.
6. Jeśli chcesz usunąć wybrany stan z modelu, wybierz stan w sekcji **Wybrane stany cyklu życia**, a następnie wybierz przycisk ![strzałki wstecz](media/04-setup-for-functional-locations.png).
7. Wybierz pozycję **Aktualizacje stanu cyklu życia**, aby określić, które stany cyklu życia mogą być zgodne z wybranym stanem.
