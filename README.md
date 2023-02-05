Hello!
experiment with amend
``` import path from 'path';
import { isFile, getName, getChildren } from '@hexlet/immutable-fs-trees';

// BEGIN (write your solution here)
const findFilesByName = (tree, checkStr) => {

  const iter = (ancestry, tree) => {
    ancestry += `${getName(tree)}/`;
    const children = getChildren(tree);
    if (children.length === 0) {
      return '';
    };
    if (isFile(tree) && tree.includes(checkStr)) {
      ancestry += `${getName(tree)}/`;
      return ancestry;
    };
    return children.reduce(iter, ancestry);
  };

  return iter(tree, '');
}
export default findFilesByName;
// END
```
