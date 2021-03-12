---
title: Właściciele produktów
description: Ten temat zawiera informacje dotyczące właścicieli produktów. Właściciele produktów to grupa użytkowników odpowiedzialnych za określone produkty. Tylko członkowie grupy mogą zwolnić te produkty. Właściciel produktu może być również używany w przepływie pracy zatwierdzania.
author: t-benebo
manager: tfehr
ms.date: 09/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EngChgProductOwner
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-09-28
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 90f5596f9b5fc45e78cc49a3309c45864e07e70b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967340"
---
# <a name="product-owners"></a>Właściciele produktów

[!include [banner](../includes/banner.md)]

Właściciele produktu to grupa użytkowników odpowiedzialnych za określone produkty. Gdy grupa właściciela produktu jest przypisana do produktu, tylko członkowie tej grupy mogą zwolnić produkt. Właściciel produktu może być również używany w przepływie pracy zatwierdzania w zarządzaniu zmianami inżynieryjnymi.

Właściciele produktów są ustawieniami globalnymi. Z tego względu są dostępne dla wszystkich firm.

## <a name="create-a-product-owner-group"></a>Tworzenie grupy właścicieli produktów

Aby utworzyć grupę właścicieli produktów i dodać do niej członków, należy wykonać następujące kroki.

1. Przejdź do **Zarządzanie zmianami projektowymi \> Konfiguracja \> Właściciele produktów**.
2. W okienku akcji wybierz opcję **Nowy**.
3. W polu **Właściciel produktu** wpisz opisową nazwę grupy produktów.
4. W polu **Nazwa** wprowadź krótki opis grupy.
5. Na skróconej karcie **Członkowie** dodaj pracowników, którzy powinni być członkami grupy.

## <a name="assign-a-product-owner-to-a-product"></a>Przypisz właściciela produktu do produktu

Aby przypisać właściciela produktu do produktu, wykonaj następujące kroki.

1. Otwórz stronę **Szczegóły produktu** odpowiedniego produktu lub produktu głównego.
1. Na skróconej karcie **Ogólnym** w polu **Właściciel produktu** należy określić nazwę odpowiedniej grupy właścicieli produktów.

Gdy właściciel produktu jest przypisany do produktu, tylko członkowie grupy właściciel produktu mogą edytować ustawienie **Właściciel produktu**.

Właściciel produktu jest również widoczny na stronie **Zwolnione produkty**.

## <a name="product-owners-and-product-releases"></a>Właściciele produktów i zwolnienia produktów

Tylko użytkownicy z grupy „właściciel produktu” mogą zwolnić ten produkt. Istnieje jednak wyjątek, gdy produkt jest elementem podrzędnym, a jego element nadrzędny jest zwalniany przez właściciela elementu nadrzędnego. Innymi słowy, jeśli produkt jest częścią BOM innego produktu, system nie sprawdza właściciela produktu dla każdej pozycji w BOM. Sprawdza tylko właściciela produktu nadrzędnego.

Na przykład produkt X jest przypisany do grupy właścicieli *Szafy projektowe*. Produkt X jest również częścią BOM produktu Y, który jest przypisany do grupy właścicieli produktów *Głośniki projektowe*. Jeśli użytkownik z grupy właścicieli produktu *Głośniki projektowe* wyda produkt Y i jego BOM, produkt X zostanie zwolniony razem z produktem Y.

## <a name="product-owners-and-approvals"></a>Właściciele produktów i zatwierdzenia

Ponieważ właściciele produktów wiedzą, czy określone zmiany inżynieryjne przyniosą korzyści ich produktom, często warto uwzględnić je jako część procesu zatwierdzania w zarządzaniu zmianami inżynierskimi. Możesz wdrożyć to podejście, ustawiając właścicieli produktów jako uczestniczących dostawców w przepływach pracy, które są używane do zarządzania zmianami inżynierskimi. Następnie system przydzieli zadania zatwierdzania w przepływach pracy w oparciu o produkty objęte żądaniami zmian inżynieryjnych i zleceniami zmian inżynieryjnych. Aby uzyskać więcej informacji, zobacz [Zarządzanie zmianami dotyczącymi produktów inżynieryjnych](engineering-change-management.md).
