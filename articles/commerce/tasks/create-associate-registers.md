---
title: Tworzenie i kojarzenie kas
description: Ta procedura przedstawia sposób tworzenia kasy w punkcie sprzedaży (POS).
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailTerminalTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 001bdd61f9266798dadae2ac7c96a4f4c19dbb94
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141460"
---
# <a name="create-and-associate-registers"></a>Tworzenie i kojarzenie kas

[!include [banner](../includes/banner.md)]

Ta procedura przedstawia sposób tworzenia kasy w punkcie sprzedaży (POS). Procedura wykorzystuje dane firmy demonstracyjnej USRT.

1. Wybierz kolejno opcje Retail i Commerce > Ustawienia kanału > Ustawienia punktu sprzedaży > Rejestry.
2. Kliknij przycisk Nowy.
3. W polu Numer rejestru wpisz identyfikator nowej kasy.
    * Identyfikator kasy zazwyczaj zawiera kody umożliwiające mapowanie rejestru do sklepu, do której należy, oraz do lokalizacji w sklepie.  
4. W polu Nazwa wprowadź opisową nazwę kasy.
5. W polu Numer sklepu wprowadź lub wybierz wartość.
6. W polu Profil sprzętu wprowadź lub wybierz wartość.
    * Profile sprzętu są używane do określania urządzeń peryferyjnych, które będą podłączone do kasy, takich jak szuflada kasowa czy drukarka paragonów.  
7. W polu Profil graficzny wprowadź lub wybierz wartość.
    * Profile graficzne są używane do określania obrazów używanych w tle okna i na stronie logowania do aplikacji punktu sprzedaży, jak również motywu przewodniego aplikacji punktu sprzedaży.  
8. W polu Numer kasy EFT w punkcie sprzedaży wpisz wartość.
    * Numer kasy EFT w punkcie sprzedaży jest używany do informowania agenta rozliczeniowego, który terminal płatniczy wysyła żądania autoryzacji. Ta wartość jest często nazywana „Identyfikatorem terminala” lub „TID”. Identyfikator TID znajduje się zwykle na nalepce na urządzeniu płatniczym.  
9. Kliknij przycisk Zapisz.

