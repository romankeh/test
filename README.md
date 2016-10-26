# test

var data = [['red', 'blue', 'green'],['small', 'medium', 'large']];

result = generateVariants(data);
console.log(result);

function generateVariants(data,prefix) {
    if (typeof prefix === 'undefined') {
        prefix = '';
    }

    var result = [];
    var attribute = data.shift();

    $.each(attribute, function(key,val) {
        if (data instanceof Array && data.length > 0) {
            result = result.concat(generateVariants(data, val + ' '));
        }
        else {
            result.push(prefix + val);
        }
    });

    return result;
}
