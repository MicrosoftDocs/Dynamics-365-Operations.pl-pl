---
title: Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B
description: W tym temacie opisano sposób konfigurowania metody płatności na konto odbiorcy dla witryn handlu elektronicznego (B2B) firmy.
author: josaw1
manager: AnnBe
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailOperations
audience: Application User, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 82dfd6ac7e97d838ef442fd6ded4a4f165fc795b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211208"
---
# <a name="configure-the-customer-account-payment-method-for-b2b-e-commerce-sites"></a>Konfigurowanie metody płatności na konto odbiorcy dla witryn handlu elektronicznego B2B

[!include [banner](../../includes/banner.md)]

W tym temacie opisano sposób konfigurowania metody płatności na konto odbiorcy dla witryn handlu elektronicznego (B2B) firmy.

Sprzadawcy detaliczni mogą akceptować różne typy płatności w zamian za produkty i usługi, które sprzedają w kanale handlu elektronicznego. Każdy typ płatności akceptowany przez sprzedawcę detalicznego musi zostać skonfigurowany w Microsoft Dynamics 365 Commerce na etapie konfiguracji systemu. W witrynach B2B handlu elektronicznego musi być obsługiwana metoda płatności konto odbiorcy (lub metoda płatności na konto). 

## <a name="prerequisites"></a>Wymagania wstępne

1. Dodaj metodę płatności konta odbiorcy w Commerce Headquarters.
2. Skojarz metodę płatności konta odbiorcy z kanałem handlu elektronicznego.
3. Upewnij się, że opcja **Zezwalaj na akonto** jest włączona dla odbiorcy w **Retail i Commerce \> Odbiorcy \> Wszyscy odbiorcy \> Ustawienia domyślne płatności** w Commerce Headquarters. Ponadto upewnij się, że parametry **Limitu kredytu** są odpowiednio ustawione dla odbiorcy w **Retail i Commerce \> Odbiorcy \> Wszysyc odbiorcy \> Kredyty i windykacja** w Commerce Headquarters. 

## <a name="enable-the-customer-account-payment-method-in-commerce-site-builder"></a>Włącz metodę płatności na koncie klienta w narzędziu do tworzenia witryn Commerce 

Aby włączyć metodę płatności dla konta klienta w narzędziu do tworzenia witryn Commerce, wykonaj następujące kroki.

1. Przejdź do **Ustawień witryny \> Rozszerzenia**.
1. Ustaw właściwość **Włącz płatności konta odbiorcy** na **Włącz dla odbiorców B2B**. 
1. Wybierz **Zapisz i opublikuj**.

> [!NOTE]
> Nowe ustawienia witryny zostaną wprowadzone dopiero po zaktualizowaniu pliku app.settings.json. Aby uzyskać więcej informacji, zobacz [Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md).

## <a name="enable-the-customer-account-payment-method-on-the-checkout-page-for-the-b2b-e-commerce-site"></a>Włącz metodę płatności na koncie klienta na stronie kasy w witrynie handlu elektronicznego B2B

Aby włączyć metodę płatności na koncie klienta na stronie kasy w witrynie handlu elektronicznego B2B, wykonaj następujące kroki.

1. W narzędziu do tworzenia witryn Commerce znajdź i edytuj stronę kasy lub fragment, który zawiera moduł kasy dla witryny handlu elektronicznego B2B.
1. W gnieździe **Kontener sekcji wyewidencjonowywania** wybierz opcję **Dodaj moduł**, a następnie dodaj moduł **Płatność na konto klienta**.
1. Umieść moduł **Płatność na konto klienta**, zaznaczając wielokropek (**...**), a następnie w razie potrzeby **Przenieś w górę** lub **Przenieś w dół**.
1. Wybierz **Zapisz**, wybierz **Zakończ edycję**, aby zaewidencjonować stronę, a następnie wybierz opcję **Publikuj**, aby ją opublikować.

## <a name="confirm-that-the-customer-account-payment-method-has-been-enabled-and-published"></a>Potwierdź, że metoda płatności na koncie odbiorcy została włączona i opublikowana

Aby potwierdzić, że metoda płatności na koncie klienta została włączona, wykonaj następujące kroki.

1. Zaloguj się w witrynie handlu elektronicznego.
1. Dodaj produkt do koszyka.
1. Przechodzenie do strony realizacji transakcji. Powinna zostać wyświetlony nowa metoda płatności na **Koncie odbiorcy**.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Konfigurowanie witryny handlu elektornicznego B2B](set-up-b2b-site.md)

[Tworzenie hierarchii modelowania organizacji dla organizacji B2B](org-model.md)

[Zarządzaj użytkownikami partnerów biznesowych w witrynach handlu elektronicznego B2B](manage-b2b-users.md)

[Ustawianie limitów ilości produktów dla witryn B2B handlu elektronicznego](quantity-limits.md)

[Aktualizacje zestawu SDK i biblioteki modułów](../e-commerce-extensibility/sdk-updates.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]