---
title: Removing workflow artifacts
intro: 'You can reclaim used {% data variables.product.prodname_actions %} storage by deleting artifacts before they expire on {% data variables.product.product_name %}.'
versions:
  fpt: '*'
  ghes: '*'
  ghec: '*'
shortTitle: Remove workflow artifacts
---

{% data reusables.actions.enterprise-github-hosted-runners %}

## Deleting an artifact

{% warning %}

**Warning:** Once you delete an artifact, it cannot be restored.

{% endwarning %}

{% data reusables.repositories.permissions-statement-write %}

{% data reusables.actions.artifact-log-retention-statement %}

{% data reusables.repositories.navigate-to-repo %}
{% data reusables.repositories.actions-tab %}
{% data reusables.repositories.navigate-to-workflow %}
{% data reusables.repositories.view-run %}
1. Under **Artifacts**, click {% octicon "trash" aria-label="Remove artifact ARTIFACT-NAME" %} next to the artifact you want to remove.

    ![Screenshot showing artifacts created during a workflow run. A trash can icon, used to remove an artifact, is outlined in dark orange.](/assets/images/help/repository/actions-delete-artifact-updated.png)

## Setting the retention period for an artifact

Retention periods for artifacts and logs can be configured at the repository, organization, and enterprise level. For more information, see {% ifversion fpt or ghec or ghes %}"[AUTOTITLE](/actions/learn-github-actions/usage-limits-billing-and-administration#artifact-and-log-retention-policy)."{% elsif ghae %}"[AUTOTITLE](/repositories/managing-your-repositorys-settings-and-features/enabling-features-for-your-repository/managing-github-actions-settings-for-a-repository#configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-repository)," "[AUTOTITLE](/organizations/managing-organization-settings/configuring-the-retention-period-for-github-actions-artifacts-and-logs-in-your-organization)," or "[AUTOTITLE](/admin/policies/enforcing-policies-for-your-enterprise/enforcing-policies-for-github-actions-in-your-enterprise#enforcing-a-policy-for-artifact-and-log-retention-in-your-enterprise)."{% endif %}

You can also define a custom retention period for individual artifacts using the `actions/upload-artifact` action in a workflow. For more information, see "[AUTOTITLE](/actions/using-workflows/storing-workflow-data-as-artifacts#configuring-a-custom-artifact-retention-period)."

## Finding the expiration date of an artifact

You can use the API to confirm the date that an artifact is scheduled to be deleted. For more information, see the `expires_at` value returned by "[AUTOTITLE](/rest/actions#artifacts)."
