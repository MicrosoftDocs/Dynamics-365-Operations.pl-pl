---
title: "Konfiguracje wniosku o nowego dostawcę"
description: "W tym temacie opisano pola, których wypełnienie jest wymagane w nowym wniosku o nowego dostawcę."
author: mkirknel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: VendProspectiveVendorRegistrationConfig
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.3
ms.translationtype: HT
ms.sourcegitcommit: ba426692e2e404ab75e5730b8205115fc59e402f
ms.openlocfilehash: e9b22a6f846607e8afc5d4f01c685f1364b1c01d
ms.contentlocale: pl-pl
ms.lasthandoff: 02/08/2018

---

# <a name="vendor-request-configurations"></a>Konfiguracje wniosku o nowego dostawcę
[!INCLUDE [banner](../includes/banner.md)]

Aby utworzyć wniosek o nowego dostawcę, osoba kontaktowa dostawcy musi ukończyć kreatora rejestracji potencjalnego dostawcy.

W formularzu **Konfiguracje wniosku o nowego dostawcę** można utworzyć profile określające wymagane i widoczne pola w kreatorze rejestracji potencjalnego dostawcy.

Kreator rejestracji dostawcy rozpocznie od pytania użytkownika-potencjalnego dostawcy o kraj/region, w którym dostawca prowadzi działalność. Ta informacja wpływa na wybór odpowiedniej konfiguracji. W przypadku niezdefiniowania określonej konfiguracji dla kraju/regionu zostanie użyta konfiguracja domyślna.

### <a name="set-up-a-vendor-request-configuration"></a>Definiowanie konfiguracji wniosku o nowego dostawcę

Domyślnie konfiguracja dostawcy jest dostępna w formularzu konfiguracji wniosku o nowego dostawcę.

Wybór kraju/regionów dla konfiguracji domyślnej jest niemożliwy, dlatego nie można wprowadzić zmian w sekcji **Kraje/regiony**.

1. Kliknij kolejno opcje **Zaopatrzenie i sourcing** > **Konfiguracja** > **Dostawcy**, a następnie kliknij opcję **Konfiguracje wniosku o nowego dostawcę**.
2. Kliknij kartę **Pola** , aby ustawić stan wymienionych pól.
3. Ukryte (niewidoczne)
4. Wyświetlane (widoczne, ale nieobowiązkowe)
5. Wymagane (widoczne i obowiązkowe)
6. Kliknij kartę **Zawartość**, aby określić, czy tekst ma być widoczny w kreatorze oraz czy ma być dostępne potwierdzenie, które potencjalny dostawca musi zaakceptować przed przejściem do następnego krok w kreatorze. Potwierdzenie będzie wymagane w przypadku wszystkich warunków i zasad, które użytkownik musi zaakceptować w celu kontynuacji.

Można także wprowadzić komunikat potwierdzenia, który zostanie wyświetlony po zakończeniu pracy kreatora. Można też dodać co najmniej jeden kwestionariusz.

### <a name="create-a-vendor-configuration-for-a-specific-countryregion"></a>Tworzenie konfiguracji dostawcy dla określonego kraju/regionu
1.  Kliknij kolejno opcje **Zaopatrzenie i sourcing** > **Konfiguracja** > **Dostawcy**, a następnie kliknij opcję **Konfiguracje wniosku o nowego dostawcę**.
2.  Kliknij przycisk **Nowy**, aby utworzyć nową konfigurację i podaj jej nazwę.
3.  Kliknij przycisk **Zapisz**.
4.  Otwórz kartę **Kraj/regiony**, aby wybrać kraj/region, dla którego ma zostać użyta konfiguracja.
5.  Dokończ konfigurację, postępując zgodnie ze wskazówkami dotyczącymi konfiguracji domyślnej.


