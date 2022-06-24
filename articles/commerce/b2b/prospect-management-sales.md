---
title: Zarządzaj użytkownikami partnerów biznesowych w witrynach e-commerce B2B za pomocą Dynamics 365 Sales
description: W tym artykule opisano, jak używać Microsoft Dynamics 365 Sales do zarządzania zatwierdzeniami partnerów biznesowych dla witryn internetowych Dynamics 365 Commerce business-to-business (B2B).
author: shajain
ms.date: 2/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: shajain
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: ac4aa15f2c6e7f557105254c2c8ce743a9466985
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8878628"
---
# <a name="manage-business-partner-users-on-b2b-e-commerce-websites-using-dynamics-365-sales"></a>Zarządzaj użytkownikami partnerów biznesowych w witrynach e-commerce B2B za pomocą Dynamics 365 Sales

[!include [banner](../../includes/banner.md)]

W tym artykule opisano, jak używać Microsoft Dynamics 365 Sales do zarządzania zatwierdzeniami partnerów biznesowych dla witryn internetowych Dynamics 365 Commerce business-to-business (B2B). Organizacje, które już zainwestowały w rozwiązanie Dynamics 365 Sales, mogą wykorzystać jego koncepcje potencjalnych klientów i możliwości w procesie zatwierdzania partnerów biznesowych w handlu elektronicznym B2B.

Aby uzyskać informacje o kontekście procesu zatwierdzania partnera biznesowego B2B, zobacz temat [Zarządzaj użytkownikami partnerów biznesowych w witrynach e-commerce B2B](manage-b2b-users.md).

Potencjalni partnerzy biznesowi mogą zainicjować proces wprowadzania do witryny e-commerce B2B, przesyłając żądanie włączenia za pośrednictwem łącza na stronie B2B. Po przesłaniu żądania i uruchomieniu odpowiednich zadań (takich jak **P-0001** i **Synchronizuj zamówienia i żądania kanałów**) w centrali handlowej, żądanie włączenia jest zapisywane w **Wszystkich perspektywach** strona w siedzibie Commerce. Proces zatwierdzania prospektu partnera biznesowego można następnie zakończyć w formularzu Sprzedaż.

Po włączeniu integracji między sprzedażą i sprzedażą tworzenie prospektu partnera biznesowego w handlu powoduje utworzenie *potencjalnego klienta* w sprzedaży.

Na poniższej ilustracji pokazano przykład strony tworzenia potencjalnych klientów dla prospektu partnera biznesowego w sprzedaży.

![Strona tworzenia potencjalnych klienta w Dynamics 365 Sales.](../media/LeadInSales.png)

Na ilustracji w sekcji **Kontakt** jest przedstawiana osoba, która przesłała wniosek o dołączanie, a w sekcji **Firma** jest przedstawiana organizacja. Notatka w sekcji **Osi czasu** wskazuje, że potencjalny klienta został wygenerowany przez infrastrukturę podwójnego zapisu. Ponieważ został on utworzony przez infrastrukturę podwójnego zapisu, ten potencjalny klienta nie będzie widoczny na liście rozwijanej **Moi otwarci potencjalni klienci**. Pojawi się on w nowym widoku o nazwie **Wszyscy potencjalni klienci handlu B2B**.

Zgodnie ze standardowym procesem kwalifikacji potencjalnego klienta w sprzedaży, gdy użytkownik „kwalifikuje” potencjalnego klienta, rekord *szansy sprzedaży*, rekord *kontaktu* i rekord *konta*. Infrastruktura podwójnego zapisu jest używana do zapisu rekordów kontaktów i kont w portalu Commerce. Kontakt jest tworzony jako odbiorca *typu osoba*, a firma jest tworzona jako odbiorca typu *organizacji*. Jeśli użytkownik wybierze opcję **Zamknij jako Wygrana** dla szansy sprzedaży, prospekt zostanie zatwierdzony w handlu commerce. Zatwierdzenie prospektu powoduje utworzenia hierarchii odbiorcy.

Wszystkie pozostałe procesy biznesowe występują w handlu Commerce. Te procesy obejmują wysyłanie wiadomości e-mail do partnera biznesowego, definiowanie zarządzania limitami kredytu dla użytkowników i dodawanie kolejnych użytkowników do witryny B2B. Jeśli jednak użytkownik zdyskwalifikowa potencjalnego klienta lub oznaczy szansę sprzedaży jako przegraną, a nie zakwalifikowanie potencjalnego klienta, prospekt w handlu zostanie oznaczony jako odrzucony, a do osoby żądacej zostanie wysłany odrzucenie przysłania wiadomości e-mail.

## <a name="enable-integration-between-sales-and-commerce"></a>Włącz integrację między sprzedażą a handlem

Integracja między sprzedażą i sprzedażą opiera się na infrastruktury podwójnego zapisu. Dlatego należy włączyć i pracować z dwoma zapisami, aby odbiorcy utworzeni w jednym systemie zapisywani są do drugiego. Aby uzyskać więcej informacji na temat infrastruktury podwójnego zapisu, zobacz [Omówienie funkcji podwójnego zapisu](/dynamics365/fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-overview).

Po zakończeniu konfiguracji podwójnego zapisu partner wdrożeniowy może przejść do [Microsoft AppSource](https://appsource.microsoft.com/) i wyszukać rozwiązanie o nazwie [Rozwiązania dla handlu z podwójnym zapisem](https://partner.microsoft.com/dashboard/commercial-marketplace/offers/7ca1d8c9-dc79-4cb7-a82e-8dc96a25acca/overview). Zainstaluj pakiet za pomocą kreatora standardowej instalacji, a następnie przetestuj go, tworząc prospekt w witrynie B2B. Po utworzeniu prospektu sprawdź, czy prośba jest wyświetlana na liście **Wszyscy potencjalni klienci** w obszarze Handel, a następnie sprawdź, czy potencjalny klient jest wyświetlany jako potencjalny klient w dziale Sprzedaż.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B](manage-b2b-users.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
