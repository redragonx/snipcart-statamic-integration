<template>

    <tr @dragover="dragOver" @drop="drop">
        <td>
            <div class="img">
                <a href="" @click.prevent="selectFolder(folder.path)">
                    <file-icon extension="folder"></file-icon>
                </a>
            </div>
        </td>

        <td>
            <a href="" @click.prevent="selectFolder(folder.path)">
                {{ folder.title }}
            </a>
        </td>

        <td colspan="2"></td>

        <td class="column-actions">

            <div class="btn-group" :class="{ open: showActionsDropdown }">

                <button type="button" class="btn-more dropdown-toggle"
                        aria-haspopup="true" aria-expanded="false"
                        @click="toggleActions">
                    <i class="icon icon-dots-three-vertical"></i>
                </button>

                <ul class="dropdown-menu">
                    <li>
                        <a href="" @click.prevent="editFolder">
                            {{ translate('cp.edit') }}
                        </a>
                    </li>

                    <li class="divider"></li>

                    <li class="warning">
                        <a href="#" @click.prevent="deleteFolder">
                            {{ translate('cp.delete') }}
                        </a>
                    </li>
                </ul>

            </div>

        </td>
    </tr>

</template>


<script>
import Folder from './Folder';
import Row from './Row';

export default {

    mixins: [Folder, Row],

}
</script>
